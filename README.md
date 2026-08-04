# Grid Status (gridstatus)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Grid Status is a United States electricity grid and power market data platform. The hosted Grid Status API (`api.gridstatus.io`) exposes hundreds of curated datasets - day-ahead and real-time LMP and settlement point prices, load and load forecasts, fuel mix, ancillary services, storage, and transmission constraints - across CAISO, ERCOT, PJM, MISO, NYISO, SPP, ISONE, and IESO through a uniform dataset query model. Grid Status also maintains the open-source `gridstatus` Python library (BSD-3-Clause) for pulling raw data directly from ISO/RTO sources, and the `gridstatusio` client for the hosted API.

Access model: the hosted API requires an API key (from the [settings page](https://www.gridstatus.io/settings/api)) passed in the `x-api-key` header, with a free tier documented at 500,000 rows returned per month and paid plans that raise row and rate limits and unlock premium endpoints such as daily peak reports. The live OpenAPI 3.1 document is published at [api.gridstatus.io/openapi.json](https://api.gridstatus.io/openapi.json). Exact paid tier prices are only published on the JavaScript pricing page and are not reconciled in this entry.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/gridstatus/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/gridstatus/refs/heads/main/apis.yml)

## Tags

- Day-Ahead Prices
- Electricity
- Grid Data
- Energy Markets
- LMP
- Load
- Fuel Mix
- Open Source

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Grid Status Datasets API

Browse the Grid Status data catalog programmatically - list every published dataset you have access to, and fetch per-dataset metadata including description, earliest and latest available time, columns, primary keys, source URL, data frequency, and publication frequency. Audit and updates endpoints report ingest history and row-level insert/update counts per dataset.

- **Human URL:** [https://docs.gridstatus.io/developers/api-reference/dataset-metadata](https://docs.gridstatus.io/developers/api-reference/dataset-metadata)
- **Base URL:** `https://api.gridstatus.io/v1`

#### Tags

- Datasets
- Metadata
- Catalog

#### Properties

- [Documentation](https://docs.gridstatus.io/developers/getting-started)
- [API Reference](https://docs.gridstatus.io/developers/api-reference/dataset-metadata)
- [OpenAPI](openapi/gridstatus-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/gridstatus.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gridstatus.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Grid Status Dataset Query API

The workhorse of the platform - query any dataset by ID (for example `ercot_spp_day_ahead_hourly`, `ercot_fuel_mix`, `caiso_load`, `caiso_lmp_real_time_5_min`, `pjm_lmp_real_time_5_min`, `ercot_as_prices`) with time-range and column filters, ordering, resampling to frequencies from 1 minute to 1 year, pagination with cursors, and JSON or CSV output. Covers day-ahead and real-time prices, kWh/MWh rates, load, fuel mix, storage, and balancing data across all supported ISOs.

- **Human URL:** [https://docs.gridstatus.io/developers/api-reference/query-data](https://docs.gridstatus.io/developers/api-reference/query-data)
- **Base URL:** `https://api.gridstatus.io/v1`

#### Tags

- Day-Ahead Prices
- LMP
- Load
- Fuel Mix

#### Properties

- [Documentation](https://docs.gridstatus.io/developers/concepts/query-parameters)
- [API Reference](https://docs.gridstatus.io/developers/api-reference/query-data)
- [OpenAPI](openapi/gridstatus-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/gridstatus.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gridstatus.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Grid Status Pricing Locations API

Look up the pricing locations (nodes, hubs, and zones) behind LMP datasets - list locations, fetch a single location by Grid Status entity ID, and find pricing locations near a latitude/longitude point to map physical assets to the correct settlement location.

- **Human URL:** [https://docs.gridstatus.io/developers/api-reference/pricing-locations](https://docs.gridstatus.io/developers/api-reference/pricing-locations)
- **Base URL:** `https://api.gridstatus.io/v1`

#### Tags

- Pricing Locations
- Nodes
- Hubs

#### Properties

- [API Reference](https://docs.gridstatus.io/developers/api-reference/pricing-locations)
- [OpenAPI](openapi/gridstatus-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/gridstatus.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gridstatus.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Grid Status Constraints API

Transmission constraint analytics - list constraints and contingencies, fetch binding intervals, binding counts and costs by period, constraint stats, heat maps, and shift factors both per constraint and per pricing location, for congestion analysis and constraint impact studies.

- **Human URL:** [https://docs.gridstatus.io/developers/api-reference/constraints](https://docs.gridstatus.io/developers/api-reference/constraints)
- **Base URL:** `https://api.gridstatus.io/v1`

#### Tags

- Constraints
- Congestion
- Shift Factors

#### Properties

- [API Reference](https://docs.gridstatus.io/developers/api-reference/constraints)
- [OpenAPI](openapi/gridstatus-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/gridstatus.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gridstatus.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Grid Status Reports and Block Pricing API

Pre-computed market summaries - volume-weighted block-averaged prices (daily plus month-to-date summaries) for an ISO over a date range, and daily peak reports of day-ahead market LMP peaks per zone (daily peak reports require a paid Grid Status plan).

- **Human URL:** [https://docs.gridstatus.io/developers/api-reference/block-pricing-data](https://docs.gridstatus.io/developers/api-reference/block-pricing-data)
- **Base URL:** `https://api.gridstatus.io/v1`

#### Tags

- Block Pricing
- Reports
- Day-Ahead Prices

#### Properties

- [Documentation](https://docs.gridstatus.io/developers/api-reference/block-pricing-data)
- [API Reference](https://docs.gridstatus.io/developers/api-reference/reports)
- [OpenAPI](openapi/gridstatus-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/gridstatus.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gridstatus.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Grid Status Bulk Exports and Usage API

Operational surface for heavy consumers - list per-day bulk CSV export files for a dataset and generate presigned S3 URLs to download them, and check your API usage (rows returned, requests, and per-second/minute/hour rate limits) against your plan for the current billing period.

- **Human URL:** [https://docs.gridstatus.io/developers/bulk-csv-downloads/getting-started](https://docs.gridstatus.io/developers/bulk-csv-downloads/getting-started)
- **Base URL:** `https://api.gridstatus.io/v1`

#### Tags

- CSV Exports
- Bulk Data
- API Usage

#### Properties

- [Documentation](https://docs.gridstatus.io/developers/bulk-csv-downloads/getting-started)
- [API Reference](https://docs.gridstatus.io/developers/api-reference/api-usage)
- [OpenAPI](openapi/gridstatus-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/gridstatus.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gridstatus.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/gridstatus)
- [LinkedIn](https://www.linkedin.com/company/grid-status)
- [Website](https://www.gridstatus.io)
- [Documentation](https://docs.gridstatus.io)
- [Plans](plans/gridstatus-plans-pricing.yml)
- [Rate Limits](rate-limits/gridstatus-rate-limits.yml)
- [Fin Ops](finops/gridstatus-finops.yml)
- [Blog](https://blog.gridstatus.io/rss/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
