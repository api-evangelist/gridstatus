# Grid Status (gridstatus)

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
