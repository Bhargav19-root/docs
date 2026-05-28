# API Documentation Change Recommendations

Based on exhaustive black-box testing (26 tests, T01–T26) against `https://api.linkutm.com/api/v1` using a live API key and workspace slug "trail".

---

## 1. `x-workspace-id` header — marked Required incorrectly across all Links endpoints

**Affected files:**
- `docs/api/links-create.mdx`
- `docs/api/links-get.mdx` (list + single)
- `docs/api/links-update.mdx`
- `docs/api/links-delete.mdx`

**Current doc claim:**

| Header | Required |
|--------|----------|
| `x-workspace-id: <uuid_or_slug>` | Yes |

**Actual behavior:** When authenticating with an API key (`lk_live_`), the header is **optional**. The auth guard extracts the workspace from the key and injects it automatically. Passing a mismatched workspace ID returns `401`; passing the correct one or omitting it both succeed.

**Tests proving this:** T01, T02, T03, T12, T13 — all returned 2xx with no `x-workspace-id` header.

**Recommended fix:** Change the Required column to conditional:

| Header | Required |
|--------|----------|
| `x-workspace-id: <uuid_or_slug>` | Yes (JWT); Optional (API key — inferred from key) |

Add a note under the header table:

> **API key auth:** The `x-workspace-id` header is optional. The key is workspace-scoped, so the workspace is resolved automatically. If you include the header it must match the key's workspace or the request is rejected with `401`.

---

## 2. `docs/api/introduction.mdx` — Contradictory statement about `x-workspace-id`

**Current text (Note block):**

> Without it, the call returns `404` or `400`.

**Problem:** This is only true for JWT auth. For API key auth the header is optional and the call succeeds without it. This contradicts the correct statement already present later in the introduction:

> A key is bound to the workspace it was created in, so the `x-workspace-id` header is optional when you authenticate with a key.

**Recommended fix:** Update the Note block to:

> For JWT auth, every workspace-scoped endpoint requires this header; without it the call returns `404` or `400`. For API key auth the header is optional — the key already encodes the workspace.

---

## 3. `POST /links` — Missing `url` field returns `500` instead of `400`

**Endpoint:** `POST /api/v1/links`

**Test:** T04 — sent `{}` (no `url` field) with a valid API key.

**Expected:** `400 Bad Request` — consistent with docs: "400 — Validation failure: missing required fields."

**Actual:** `500 Internal Server Error`

**Recommended fix in docs:** Add a caveat under the Errors table in `links-create.mdx`:

> **Note:** Omitting the `url` field currently returns `500` instead of `400`. This is a backend bug. Treat `500` on link creation as a possible validation error until fixed.

**Recommended backend fix (separate ticket):** Add a `@IsNotEmpty()` / `@IsUrl()` guard on the `url` field in the `CreateLinkDto` so NestJS validation pipe rejects it with `400` before the service layer is reached.

---

## 4. `GET /links/:id/tags` with API key — returns `404 "Cannot GET"` not `401`

**Endpoint:** `GET /api/v1/links/:id/tags`

**Test:** T15 — called with a valid API key.

**Expected:** `401 Unauthorized` (consistent with T08–T11, T14, T16–T17, T26 which all returned `401` for endpoints outside API key scope).

**Actual:** `{"message":"Cannot GET /api/v1/links/…/tags","error":"Not Found","statusCode":404}`

**Implication:** The route `/links/:id/tags` is either not registered or is mounted at a different path. Docs (if they reference this endpoint) incorrectly describe it as returning `401` for API keys.

**Recommended fix:** Either:
1. Register the route and gate it properly (returns `401` for API keys).
2. Remove the endpoint from the docs until it's implemented.

If the route is intentionally absent, document clearly: "Tags for a specific link are fetched via `GET /tags?linkId=<id>`, not `GET /links/:id/tags`."

---

## 5. `GET /links` — `orderBy` query parameter works but is undocumented

**Endpoint:** `GET /api/v1/links`

**Test:** T18 — `GET /links?orderBy=clicks` returned `200` with links sorted by click count.

**Current docs:** Query params section does not list `orderBy`.

**Recommended fix:** Add to the query params table in `links-get.mdx`:

| Param | Type | Description |
|-------|------|-------------|
| `orderBy` | string | Sort field. Accepted values: `clicks`, `createdAt`, `updatedAt`, `title`. Default: `createdAt`. |
| `order` | string | Sort direction: `asc` or `desc`. Default: `desc`. |

_(Verify accepted values against service code before publishing — `clicks` is confirmed working.)_

---

## 6. `POST /links` — `domainId` and `customUtmParams` fields work but docs inconsistency

**Tests:** T06 (domainId), T07 (customUtmParams) — both returned `201` successfully.

**Observation:** The NestJS controller type definition does not explicitly list `domainId` or `customUtmParams` in the `@Body()` destructuring. However, both fields are accepted and processed by the service layer. This means NestJS strips unknown fields at the controller but the service receives them through a separate path — or the controller does accept them silently.

**Action required:** Verify in `links.service.ts` / `CreateLinkDto` that these fields are formally declared so they are not accidentally broken by a future NestJS `whitelist: true` validation config change. No doc change needed if they are already documented; confirm they remain in `links-create.mdx` body params list.

---

## 7. UTM normalization — behavior matches docs

**Test:** T20 — created a link with uppercase UTM values (`UTM_SOURCE=Google`, `UTM_MEDIUM=CPC`, `UTM_CAMPAIGN=Q2_Launch`). Stored and returned as lowercase (`google/cpc/q2_launch`).

**Status:** Docs correctly describe normalization (forceLowercase). No change needed. ✅

---

## 8. Summary table — endpoints reachable with API key

The docs should make it explicit which endpoints accept API key auth. Currently this is scattered. Recommend adding a dedicated table to `docs/api/api-keys.mdx`:

| Endpoint | API Key Supported |
|----------|------------------|
| `GET /links` | ✅ |
| `GET /links/stats` | ✅ |
| `GET /links/ids` | ✅ |
| `GET /links/:id` | ✅ |
| `POST /links` | ✅ |
| `PATCH /links/:id` | ✅ |
| `DELETE /links/:id` | ✅ |
| `GET /links/:id/analytics` | ❌ — returns `401` |
| `GET /links/:id/tags` | ❌ — route not found (`404`) |
| `GET /analytics` | ❌ — returns `401` |
| `GET /templates` | ❌ — returns `401` |
| `GET /folders` | ❌ — returns `401` |
| `GET /tags` | ❌ — returns `401` |
| `GET /utm-rules` | ❌ — returns `401` |
| `POST /pixels` | ❌ — returns `401` |

---

## Test run metadata

- **Date:** 2026-05-28
- **API key:** `lk_live_e0269a24...` (workspace: trail)
- **Plan:** Agency
- **Total tests:** 26 (T01–T26)
- **Passed:** 22 ✅
- **Failed / discrepancies found:** 4 ❌ (T04, T15, T18 undocumented, introduction Note)
