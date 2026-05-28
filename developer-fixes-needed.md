# Backend Fixes Needed

Issues found during black-box API testing (2026-05-28) where the **docs are correct** and the **implementation needs to change**.

---

## Fix 1 — `POST /links` with missing `url` returns `500` instead of `400`

### Reproduction

```bash
curl -X POST https://api.linkutm.com/api/v1/links \
  -H "Authorization: Bearer lk_live_<key>" \
  -H "Content-Type: application/json" \
  -d '{}'
```

**Expected:** `400 Bad Request` — docs say "400 — Validation failure: missing required fields."

**Actual:** `500 Internal Server Error`

### Root cause

The `url` field on the `CreateLinkDto` (or the inline body type in the controller) is not decorated with a NestJS validation decorator (`@IsNotEmpty()`, `@IsUrl()`, etc.). NestJS's `ValidationPipe` therefore passes through an empty/missing `url`, and the service layer crashes attempting to process it, producing an unhandled exception.

### Fix

In `src/links/dto/create-link.dto.ts` (or wherever the DTO is defined), add validators to the `url` field:

```typescript
import { IsNotEmpty, IsUrl } from 'class-validator';

@IsNotEmpty({ message: 'url is required' })
@IsUrl({}, { message: 'url must be a valid URL' })
url: string;
```

Ensure `ValidationPipe` is applied globally (or on the controller) with `whitelist: true` if not already:

```typescript
// main.ts
app.useGlobalPipes(new ValidationPipe({ whitelist: true }));
```

**Expected result after fix:** Missing or invalid `url` → `400 Bad Request` with a validation error body.

---

## Fix 2 — `GET /links/:id/tags` returns `404 "Cannot GET"` — route not registered

### Reproduction

```bash
curl https://api.linkutm.com/api/v1/links/<link-id>/tags \
  -H "Authorization: Bearer lk_live_<key>"
```

**Expected:** `401 Unauthorized` (consistent with all other sub-resource endpoints that reject API keys, e.g. `/links/:id/analytics`).

**Actual:** `{"message":"Cannot GET /api/v1/links/<id>/tags","error":"Not Found","statusCode":404}`

The `404 "Cannot GET"` is NestJS's fallback for an unregistered route — not a service-layer 404 for a missing resource. The route itself does not exist.

### Fix options

**Option A — Register the route and gate it (recommended):**

Add a `GET /links/:id/tags` endpoint in the Links controller that returns the tags for the link. Gate it with `JwtAuthGuard` only (not `JwtOrApiKeyGuard`) so API keys correctly receive `401` instead of `404`.

```typescript
@UseGuards(JwtAuthGuard)
@Get(':id/tags')
async getLinkTags(@Param('id') id: string, @Headers('x-workspace-id') workspaceId: string) {
  return this.linksService.getTagsForLink(workspaceId, id);
}
```

**Option B — Remove from docs (if the route is intentionally absent):**

If tag retrieval per-link is meant to be done via `GET /tags?linkId=<id>`, document that explicitly and remove any reference to `GET /links/:id/tags`. _(Docs currently do not explicitly document this route, but the introduction page lists it in the API key scope section.)_

---

## Summary

| # | Endpoint | Expected | Actual | Fix |
|---|---|---|---|---|
| 1 | `POST /links` (missing `url`) | `400` | `500` | Add `@IsNotEmpty` / `@IsUrl` to `url` field in DTO |
| 2 | `GET /links/:id/tags` | `401` (API key) | `404 "Cannot GET"` | Register route or document correct alternative |
