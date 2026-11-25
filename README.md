# Ghana Revenue Authority (Customs) Exchange Rates API — icumsgh-exchange-rate

[![npm version](https://img.shields.io/npm/v/icumsgh-exchange-rate.svg)](https://www.npmjs.com/package/icumsgh-exchange-rate)
[![license](https://img.shields.io/npm/l/icumsgh-exchange-rate.svg)](https://github.com/AllRates-Today/icumsgh-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/icumsgh-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/GHS today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Ficumsgh%3Fsource%3DUSD%26target%3DGHS&query=%24.rate&label=USD%2FGHS%20official%2C%20Ghana%20Revenue%20Authority%20(Customs)&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/tax-authority-rates-api/icumsgh/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Ficumsgh%3Fsource%3DUSD%26target%3DGHS&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/tax-authority-rates-api/icumsgh/)

**Official Ghana Revenue Authority (Customs) (Ghana) weekly exchange rates for Node.js and TypeScript. The published tax authority rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Ghana Revenue Authority (Customs) itself prints, every week.**

## 🚀 Why this client?

- 🏛️ **Official rates** — Ghana Revenue Authority (Customs)'s own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2020** — point-in-time tables and daily series for any past date
- 🔀 **Official vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Ghana Revenue Authority (Customs) itself published, fixed once printed and carrying the tax authority's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📈 Latest official table

[![Latest Ghana Revenue Authority (Customs) table](https://allratestoday.com/api/open/central-bank/icumsgh/table.svg)](https://allratestoday.com/tax-authority-rates-api/icumsgh/)

The image is rendered live from the keyless endpoint, so it follows the tax authority's publications on npm and on GitHub alike without a new release. The same table as text is folded below for search and copy-paste: on GitHub [a daily Action](.github/workflows/daily-table.yml) refreshes it whenever the tax authority publishes a new table; on npm it is as of the package's publish date.

<!-- daily-table:start -->
<details>
<summary>Table as text: published 2026-11-24 by Ghana Revenue Authority (Customs) — 30 rates. Updated 2026-11-25.</summary>

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AUD | GHS | buy | 7.8501 |
| AUD | GHS | sell | 7.8501 |
| CAD | GHS | buy | 8.2431 |
| CAD | GHS | sell | 8.2431 |
| CHF | GHS | buy | 14.0619 |
| CHF | GHS | sell | 14.0619 |
| CNY | GHS | buy | 1.7694 |
| CNY | GHS | sell | 1.7694 |
| DKK | GHS | buy | 1.7345 |
| DKK | GHS | sell | 1.7345 |
| EUR | GHS | buy | 12.9635 |
| EUR | GHS | sell | 12.9635 |
| GBP | GHS | buy | 15.4681 |
| GBP | GHS | sell | 15.4681 |
| JPY | GHS | buy | 0.0743 |
| JPY | GHS | sell | 0.0743 |
| NGN | GHS | buy | 0.0085 |
| NGN | GHS | sell | 0.0085 |
| NOK | GHS | buy | 1.2092 |
| NOK | GHS | sell | 1.2092 |
| NZD | GHS | buy | 6.4827 |
| NZD | GHS | sell | 6.4827 |
| SEK | GHS | buy | 1.1565 |
| SEK | GHS | sell | 1.1565 |
| USD | GHS | buy | 11.8059 |
| USD | GHS | sell | 11.8059 |
| XOF | GHS | buy | 0.0198 |
| XOF | GHS | sell | 0.0198 |
| ZAR | GHS | buy | 0.6765 |
| ZAR | GHS | sell | 0.6765 |

</details>

Source: [Official rates published by ICUMSGH, served by AllRatesToday](https://allratestoday.com/tax-authority-rates-api/icumsgh/). Rates are as printed by the tax authority; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 📦 Installation

```bash
npm install icumsgh-exchange-rate
```

```bash
yarn add icumsgh-exchange-rate
```

```bash
pnpm add icumsgh-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/icumsgh-exchange-rate`](https://www.npmjs.com/package/@allratestoday/icumsgh-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'icumsgh-exchange-rate';

const pair = await getRate('USD', 'GHS', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Ghana Revenue Authority (Customs) rate, on the tax authority's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest official table
- [Full official table](#full-official-table) — everything the tax authority printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the tax authority does not print directly are resolved from its table and flagged (see *Official vs derived rates* below).

```js
const pair = await getRate('USD', 'GHS', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'icumsgh',
  name: 'Ghana Revenue Authority (Customs)',
  rate_date: '2026-11-24',   // Ghana Revenue Authority (Customs)'s own publication date
  source: 'USD',
  target: 'GHS',
  rate: 11.8059,
  rate_type: 'sell',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full official table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'icumsgh-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'icumsgh',
  name: 'Ghana Revenue Authority (Customs)',
  rate_date: '2026-11-24',
  rates: [
    { "base": "USD", "quote": "GHS", "type": "sell", "value": 11.8059 },
    { "base": "USD", "quote": "GHS", "type": "buy", "value": 11.8059 },
    // … the rest of the official table (15 currencies vs GHS)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2020 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'icumsgh-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'GHS' });
```

**Response:**

```javascript
{
  bank: 'icumsgh',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'icumsgh-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'GHS', from: '2026-01-01', to: '2026-11-24' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'icumsgh',
  source: 'USD',
  target: 'GHS',
  from: '2026-01-01',
  to: '2026-11-24',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-11-24', rate: 11.8059, rate_type: 'sell', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Ghana Revenue Authority (Customs) currently publishes rates covering **15 currencies** against the GHS (as of the latest table):

🇦🇺 `AUD` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇳 `CNY` · 🇩🇰 `DKK` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇯🇵 `JPY` · 🇳🇬 `NGN` · 🇳🇴 `NOK` · 🇳🇿 `NZD` · 🇸🇪 `SEK` · 🇺🇸 `USD` · `XOF` · 🇿🇦 `ZAR`

## 🏛️ Source

The weekly exchange rates the Ghana Revenue Authority's Customs Division loads into ICUMS, the national customs clearance system, normally valid Tuesday to Monday. Customs uses them to convert the value of imports into cedis for duties and taxes.

- Publisher's own page: [Weekly customs exchange rates (ICUMS)](https://external.unipassghana.com/co/exchangerate/selectExchangeRateUserDetail.do?MENU_ID=IIM01S01V06) · [external.unipassghana.com](https://external.unipassghana.com/)
- Publication: every week; the exact schedule, freshness status and any current delay are on the [Ghana Revenue Authority (Customs) rates page](https://allratestoday.com/tax-authority-rates-api/icumsgh/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Ghana Revenue Authority (Customs) quotes **GHS per 1 unit of foreign currency** (e.g. `base: "USD", quote: "GHS"` means GHS per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the tax authority's series a row belongs to (`sell` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Ghana Revenue Authority (Customs) rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/icumsgh/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('icumsgh')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate icumsgh ...` command
- Evaluating? Agents can self-issue a trial key with no signup: `POST https://allratestoday.com/api/agent/keys` (send `Content-Type: application/json`) returns a 100-call key valid 7 days that covers the free-plan methods (latest table, pairs); dated tables and history need a [paid plan](https://allratestoday.com/pricing/). The MCP servers expose it as `request_trial_key`
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Official vs derived rates

If Ghana Revenue Authority (Customs) does not print a pair directly, the API resolves it from the tax authority's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The tax authority printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via GHS from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Ghana Revenue Authority (Customs) |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'icumsgh-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('icumsgh-exchange-rate');

getRate('USD', 'GHS', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once a week — cache the official table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the official table |
| `getLatestRates({ apiKey })` | Free | The tax authority's full latest official table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2020 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same official tables are mirrored daily as open data:

- Hugging Face: [AllRatesToday/central-bank-exchange-rates](https://huggingface.co/datasets/AllRatesToday/central-bank-exchange-rates) — one CSV per institution (`rates/icumsgh.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- Raw JSON on GitHub: `https://raw.githubusercontent.com/AllRates-Today/central-bank-exchange-rates/main/data/icumsgh/latest.json`

## 🔗 Links

- **Website:** [allratestoday.com](https://allratestoday.com)
- [Ghana Revenue Authority (Customs) rates page](https://allratestoday.com/tax-authority-rates-api/icumsgh/) — live table, publication cadence, FAQ
- [All tax authority sources](https://allratestoday.com/tax-authority-rates-api/) · [Full list of 120+ central banks and 50+ tax authorities](https://allratestoday.com/central-bank-rates-api/institutions/) — one API, the same response shape for every source
- [Download central bank rates](https://allratestoday.com/download-central-bank-rates/) — every bank's latest table and history as Excel, CSV or JSON
- [Bank Exchange Rate API](https://allratestoday.com/bank-exchange-rate-api/) — live buy and sell rates from 1,200+ commercial banks in 120+ countries · [npm](https://www.npmjs.com/package/bank-exchange-rates) · [GitHub](https://github.com/AllRates-Today/bank-exchange-rates)
- [Package docs on the site](https://allratestoday.com/docs/sdk/icumsgh-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (Free)](https://allratestoday.com/register) · [Dashboard](https://allratestoday.com/profile) · [Pricing](https://allratestoday.com/pricing/)
- [Status](https://allratestoday.com/status)
- [Postman collection](https://allratestoday.com/postman/)
- [ChatGPT app](https://chatgpt.com/plugins/plugin_asdk_app_6ae1e76098f48191a285ac3f5ab7a83b) — ask ChatGPT for live and official central bank rates
- [OpenAPI reference on Bump.sh](https://bump.sh/allratestoday/doc/allratestoday-api) — also on [SwaggerHub](https://app.swaggerhub.com/apis-docs/allratestoday/allratestoday-exchange-rate-central-bank-rates-api/2.2.0)
- [GitHub](https://github.com/AllRates-Today/icumsgh-exchange-rate)

## 📜 License

MIT
