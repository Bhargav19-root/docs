# Linkutm Analytics Test Runner

Standalone CLI for testing Linkutm short-link analytics.

It uses Playwright only for the Linkutm dashboard flow, then generates public short-link clicks through lightweight HTTP requests. When both a Bright Data API key and zone/product name are provided, click generation uses the Bright Data REST request API. Otherwise it uses direct requests from the local machine.

## Install

```powershell
npm install
```

If Playwright browsers are not already installed:

```powershell
npx playwright install chromium
```

## Run

```powershell
npm start
```

The runner prompts for:

- Linkutm email
- Linkutm password
- Number of clicks
- Bright Data API key, optional
- Bright Data zone/product name, optional

Defaults:

- Concurrency: `5`
- No referrer
- Reset analytics before test
- First workspace after login
- Top visible link on the Links page

## Environment Overrides

- `LINKUTM_BASE_URL`: defaults to `https://app.linkutm.com`
- `LINKUTM_EMAIL`: skips the email prompt when set
- `LINKUTM_PASSWORD`: skips the password prompt when set
- `CLICK_COUNT`: skips the click-count prompt when set
- `BRIGHTDATA_API_KEY`: skips the optional Bright Data API key prompt when set
- `BRIGHTDATA_ZONE`: skips the optional Bright Data zone/product prompt when set
- `BRIGHTDATA_REQUEST_ENDPOINT`: defaults to `https://api.brightdata.com/request`
- `HEADLESS`: set to `false` to watch the dashboard automation
- `CLICK_CONCURRENCY`: defaults to `5`

## Output

After the run completes, the CLI prints a terminal table with:

- Link title
- Short link
- Mode
- Attempted clicks
- Successful clicks
- Failed/timeouts
- Total clicks shown
- Unique visitors shown
- Devices shown
- Browsers shown
- OS shown
- Countries/regions/cities shown
- Expected generated user-agent distribution

Bright Data API verification, referrer simulation, and tracking pixel testing are intentionally out of scope for this version.
