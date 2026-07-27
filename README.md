# Vistra Corp (vistra-energy)

Vistra Corp (NYSE: VST) is an Irving, Texas integrated retail electricity and power generation company and the largest competitive power generator in the United States, operating roughly 41,000-44,000 MW of natural gas, nuclear, coal, solar and battery storage capacity alongside a retail business serving nearly 5 million residential, commercial and industrial customers across 16 states and the District of Columbia through TXU Energy, Dynegy, Ambit Energy, Energy Harbor, Homefield Energy and U.S. Gas & Electric. Its home market is the United States, where it sits on both sides of the competitive value chain, a merchant generator selling into ERCOT, PJM, ISO-NE, NYISO, MISO and CAISO, and a retail electricity provider (REP) reselling that power to end customers. Its API posture is honestly none — no developer portal, no API subdomain and no machine-readable contract of any kind was found.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vistra-energy/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vistra-energy/refs/heads/main/apis.yml)

## Tags

- Energy
- United States
- Utilities
- Electricity
- Natural Gas
- Power Generation
- Retail Energy
- Smart Metering
- Green Button
- Energy Markets
- Nuclear
- Solar
- Battery Storage
- Texas
- ERCOT

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

None. Vistra Corp publishes no public API.

Every developer-shaped host on the primary domain fails to resolve (`developer.`, `developers.`, `docs.`, `api.`, `data.` on `vistracorp.com` all return DNS failure), every conventional discovery path returns 404 (`/developers`, `/api`, `/docs`, `/data`, `/openapi.json`, `/swagger.json`, `/.well-known/openid-configuration`), and the 758-URL sitemap for TXU Energy — Vistra's largest retail brand — contains no developer or API page. No OpenAPI, AsyncAPI, GraphQL schema or Postman collection was found on any Vistra-controlled domain, so this repository has no `openapi/` directory.

The only machine-readable surface served from `vistracorp.com` is the WordPress REST API at `/wp-json/` that backs the marketing site. It is explicitly disallowed in `robots.txt`, it is CMS infrastructure rather than a product API, and it is deliberately not listed in `apis.yml`.

## Energy Data Posture

| Dimension | Finding |
| --- | --- |
| Home market | United States |
| Role in the value chain | Merchant generator + retail electricity provider. Owns no wires and no meters. |
| Mandate regime | `green-button-voluntary` |
| Mandate status | `live-claimed-unverified` |
| Data standard | Green Button / ESPI claimed by association only; no version, no conformance statement, no endpoint |
| Consumer data API | No |
| Market data open | No |
| Access gate | `customer-account-required` |
| Auth model | None published for developers; customer portal uses web session cookies |

### A mandate is not an implementation

The United States has no federal consumer energy data right. There is no ACCC, no Data Standards Body, no CDR energy designation, and no Ontario-style Green Button regulation binding this company. Green Button is an NAESB/NIST-derived open standard (Energy Services Provider Interface, ESPI) that organizations adopt because they choose to.

The one obligation-adjacent artifact that names a Vistra entity is the US Department of Energy's page at [energy.gov/data/green-button](https://www.energy.gov/data/green-button), which lists TXU Energy among 36 entities under the heading *"Utilities Committed to Implementing Green Button."* That is a voluntary, 2012-era commitment list. It compels nothing, and the page itself does not distinguish a commitment from a live implementation.

Verification was attempted and failed. TXU Energy's own live usage-help pages — the two pages that would carry a Green Button surface if one existed — make no mention of Green Button, ESPI, data download, data export, or third-party data sharing. The MyEnergy Dashboard page instead states that *"Current kWh information in MyEnergy Dashboard is based on usage provided by the Smart Meter Texas Portal. Current usage information will be approximately 48 hours old."* No Green Button Alliance certification was found for Vistra Corp or TXU Energy. No Connect My Data surface exists on any Vistra domain.

Hence `live-claimed-unverified`: the commitment is documented, the implementation is not.

### Consumer data versus market data — both closed

**Consumer data.** No third party can obtain an individual Vistra customer's usage or billing data through a documented Vistra API. The only consumer-data surface is the TXU Energy MyAccount web application at `services.txu.com`, an ASP.NET session-cookie web app that renders a dashboard to the logged-in account holder. It is a customer portal, not a developer API. The interval readings it displays originate from Smart Meter Texas, the shared ERCOT meter-data platform operated by the four Texas transmission and distribution utilities (Oncor, CenterPoint Energy, AEP Texas, TNMP). Vistra is a consumer of that platform, not a publisher of it — a developer wanting a Texas customer's authorized interval data registers as a third party with Smart Meter Texas and bypasses Vistra entirely.

**Market data.** Vistra publishes no open grid, market, dispatch, outage or generation data of its own. ERCOT, PJM, ISO-NE, NYISO, MISO, CAISO, the EIA and FERC are the bodies that publish open data *about* Vistra's fleet.

**The split.** Most energy organizations are wide open on one axis and shut on the other. Vistra is a rare double-closed case, and the reason is structural rather than cultural: a merchant generator and competitive retailer that owns no wires and no meters, operating in a country with no consumer energy data right, has no regulatory obligation to publish and no commercial reason to. The data about Vistra exists and is obtainable — just from Smart Meter Texas, the ISOs/RTOs and the EIA, never from Vistra.

### How a developer gets in

They do not. There is no signup, no application form, no reviewed access request, no published developer contact and no partner API programme. The only route to any Vistra energy data is to become a retail customer of a Vistra brand and log in to view your own account.

## Homonym warning

Searching for "Vistra API" surfaces `devportal.vistra.com` ("API Developer Portal") and `help.vistra.com` articles describing a "Vistra Incorporations API" with OAuth2 client ID and secret. **That is a different company.** Vistra Limited (`vistra.com`) is a corporate-services, fund-administration and private-client firm. It has nothing to do with Vistra Corp (`vistracorp.com`, NYSE: VST), the power company profiled here. None of that developer portal is attributed to this record.

## Common Properties

- [Website](https://www.vistracorp.com/)
- [About](https://vistracorp.com/about/)
- [Retail](https://vistracorp.com/retail/)
- [Sustainability](https://vistracorp.com/sustainability/)
- [Investor Relations](https://investor.vistracorp.com/)
- [Blog RSS](https://vistracorp.com/feed/)
- [LinkedIn](https://www.linkedin.com/company/vistra-energy)
- [Legislative Hub](https://hub.vistracorp.com/our-companies/)
- Retail brands: [TXU Energy](https://www.txu.com/) · [Dynegy](https://www.dynegy.com/) · [Ambit Energy](https://www.ambitenergy.com/) · [Homefield Energy](https://www.homefieldenergy.com/) · [TriEagle Energy](https://www.trieagleenergy.com/)
- [TXU Energy MyAccount (customer portal)](https://services.txu.com/)
- [Green Button — US DOE](https://www.energy.gov/data/green-button)
- [Smart Meter Texas (TDU-operated, not Vistra)](https://smartmetertexas.com/)

## Maintainers

- Kin Lane — kin@apievangelist.com
