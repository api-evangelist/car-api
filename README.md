# Car API / CarAPI (car-api)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

CarAPI is a developer-friendly vehicle API and database that provides programmatic access to automotive data including makes, models, trims, bodies, engines, mileage, VIN decoding, license plate decoding, OBD-II diagnostic codes, and power sports vehicle information. The platform follows a freemium model - its public vehicle dataset is available without an account, and paid plans unlock higher daily request limits and production use. The API is REST/JSON with JWT authentication and ships with OpenAPI, Swagger, ReDoc, and Postman documentation.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/car-api/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **x-type:** company
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Automobiles
- Automotive Data
- Cars
- License Plate Decoder
- OBD-II
- Power Sports
- Vehicle API
- Vehicle Specifications
- Vehicles
- VIN Decoder

## Overview

CarAPI (carapi.app) is positioned as a low-friction vehicle data platform for developers. The business model is freemium: engineers can prototype against the public dataset without creating an account, and move to a paid plan (Base $199/yr, Plus $249/yr, Premium $299/yr) when they go live. Paid tiers increase the daily API call allowance (1,500 / 3,000 / 6,000 requests per day) and include VIN decoding, OBD-II code lookups, and email support. Authentication is JWT-based: clients POST an `api_token` and `api_secret` to `/api/auth/login`, then pass the returned token as `Authorization: Bearer {jwt}` on subsequent requests. Tokens expire in seven days. The API supports JSON, JSON-LD, and HAL response formats, pagination up to 1,000 per page, JSON-query filters with operators, and modified-since caching. CORS is not supported, so integrations are server-side.

## APIs

### CarAPI Vehicle API
The CarAPI Vehicle API provides REST/JSON access to a vehicle database covering year/make/model (1900-2026), sub-models, trims (1990-2026), bodies, engines, mileage, interior, and exterior attributes. Authentication uses JWT tokens obtained from `/api/auth/login` with an `api_token` and `api_secret`. The API supports pagination (up to 1000 per page), sorting, JSON filter queries with operators, and modified-since caching. Responses are available as `application/json`, `application/ld+json`, and `application/hal+json`. CORS is not supported; the API is intended for server-side integration.

**Human URL:** [https://carapi.app/](https://carapi.app/)
**Base URL:** https://carapi.app/api

#### Features

- REST/JSON vehicle database with OpenAPI documentation
- Year/make/model coverage 1900-2026 (trims 1990-2026)
- JWT authentication via `/api/auth/login` endpoint
- Pagination, sorting, and JSON filter queries with in/>=/operators
- JSON, JSON-LD (`application/ld+json`), and HAL (`application/hal+json`) responses
- Modified-since timestamps for cache validation
- Swagger UI, ReDoc, Postman, and GitHub docs
- Public dataset available without account for prototyping

#### Use Cases

- Vehicle dropdowns and VIN-aware forms in auto-commerce apps
- Automotive marketplaces and classifieds
- Fleet management and telematics dashboards
- Insurance quoting and underwriting vehicle lookups
- Repair shop and service advisor applications
- Vehicle research and comparison tools

### CarAPI VIN Decoder API
Decodes Vehicle Identification Numbers into structured vehicle attributes including year, make, model, trim, body type, engine, transmission, and other specifications. Shares JWT authentication and the vehicle database with the main API.

**Human URL:** [https://carapi.app/features/vin-decoder-api](https://carapi.app/features/vin-decoder-api)

#### Features
- VIN to year/make/model/trim decoding
- Returns body, engine, transmission, and other specs
- Shared JWT auth with Vehicle API
- JSON/JSON-LD/HAL response formats

#### Use Cases
- Insurance and warranty quote flows
- Used-car listing auto-population
- Lienholder, title, and registration tooling
- Fleet onboarding and telematics provisioning

### CarAPI License Plate API
Decodes license plates into vehicle records for US, Canada, Australia, and other supported countries, returning year/make/model/trim and related specifications.

**Human URL:** [https://carapi.app/features/license-plate-api](https://carapi.app/features/license-plate-api)

#### Features
- License plate lookup for US, Canada, Australia, and more
- Returns structured vehicle identification data
- Shared JWT authentication with CarAPI

#### Use Cases
- Curbside appraisal and trade-in tools
- Parking, tolling, and fleet enforcement
- Repair estimate and service bay intake
- Auto insurance quote-by-plate flows

### CarAPI OBD-II Code API
Provides search and lookup across more than 9,000 OBD-II diagnostic trouble codes (DTCs) with descriptions, used in vehicle diagnostics and automotive repair software.

**Human URL:** [https://carapi.app/features/obd-codes-api](https://carapi.app/features/obd-codes-api)

#### Features
- Searchable catalog of 9,000+ OBD-II codes
- Code, description, and metadata lookup
- Shared JWT authentication with CarAPI

#### Use Cases
- DIY mechanic and consumer diagnostics apps
- Repair shop service advisor tooling
- Telematics and connected-car dashboards
- Training and educational tools

### CarAPI Power Sports API
Vehicle specifications for power sports categories such as motorcycles, ATVs, UTVs, and similar motor vehicles, following the same REST/JSON conventions as the main Vehicle API.

**Human URL:** [https://carapi.app/power-sports](https://carapi.app/power-sports)

#### Features
- Motorcycle, ATV, and UTV specifications
- Year/make/model coverage for power sports vehicles
- Shared JWT authentication with CarAPI
- JSON/JSON-LD/HAL response formats

#### Use Cases
- Power sports dealership and marketplace listings
- Insurance quote flows for motorcycles and ATVs
- Parts and accessory fitment catalogs
- Fleet and rental operations for power sports vehicles

## Common Properties

- [Website](https://carapi.app/)
- [Documentation](https://carapi.app/docs)
- [API](https://carapi.app/api)
- [Pricing](https://carapi.app/pricing)
- [Features](https://carapi.app/features)
- [FAQ](https://carapi.app/features/faq)
- [Rate Limits](https://carapi.app/docs/rate_limits/)
- [Login](https://carapi.app/login)
- [Sign Up](https://carapi.app/register)
- [Contact](https://carapi.app/contact)
- [Terms of Use](https://carapi.app/terms-of-use)
- [Privacy Policy](https://carapi.app/privacy-policy)

## Timestamps

- **Created:** 2024-07-11
- **Modified:** 2026-04-23

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
