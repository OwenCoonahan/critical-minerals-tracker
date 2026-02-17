# Critical Minerals Data Sources — Comprehensive Reference

*Last updated: 2026-02-17*

This document catalogs all major data sources for tracking critical minerals across the full value chain: production, processing, trade, pricing, company/mine-level data, supply chain, defense, real-time feeds, and geospatial.

---

## Table of Contents

1. [Production/Mining Data](#1-productionmining-data)
2. [Processing/Refining](#2-processingrefining)
3. [Trade/Import-Export](#3-tradeimport-export)
4. [Pricing](#4-pricing)
5. [Company-Level Data](#5-company-level-data)
6. [Mine-Level Data](#6-mine-level-data)
7. [Supply Chain / Downstream](#7-supply-chain--downstream)
8. [Defense-Specific](#8-defense-specific)
9. [Real-Time / Near-Real-Time Feeds](#9-real-time--near-real-time-feeds)
10. [Geospatial](#10-geospatial)

---

## 1. Production/Mining Data

### USGS National Minerals Information Center (NMIC)
- **URL:** https://www.usgs.gov/centers/national-minerals-information-center
- **Data:** Annual production, reserves, imports/exports, consumption, prices for ~90 mineral commodities across all countries
- **Key publications:**
  - **Mineral Commodity Summaries** (annual, January) — 2-page profiles per commodity with world production, US supply/demand, prices
  - **Minerals Yearbook** (annual, lag ~2 years) — detailed country-by-country data
  - **Mineral Industry Surveys** (monthly/quarterly) — current production data for select commodities
- **Format:** PDF reports + downloadable data tables (XLSX, CSV)
- **Update frequency:** Annual (Commodity Summaries in Jan); Monthly/Quarterly for surveys
- **Cost:** FREE
- **Coverage:** ~90 minerals, global (180+ countries)
- **Programmatic access:**
  - Bulk download: https://www.usgs.gov/centers/national-minerals-information-center/commodity-statistics-and-information
  - Data tables as XLSX: https://pubs.usgs.gov/periodicals/mcs2025/
  - Historical data series (DS140): https://www.usgs.gov/centers/national-minerals-information-center/historical-statistics-for-mineral-and-material
  - No official API; scraping XLSX/CSV downloads is straightforward
  - Data also available via USGS ScienceBase: https://www.sciencebase.gov/

### British Geological Survey (BGS) — World Mineral Statistics
- **URL:** https://www.bgs.ac.uk/mineralsuk/statistics/home.html
- **Data:** Global mineral production statistics, 1913–present. Country-by-country production for ~70 minerals
- **Format:** Interactive database + downloadable CSV/XLSX
- **Update frequency:** Annual
- **Cost:** FREE
- **Coverage:** ~70 minerals, global
- **Programmatic access:**
  - Download portal: https://www2.bgs.ac.uk/mineralsUK/statistics/worldStatistics.html
  - Bulk CSV available after selecting commodity/country
  - No API; CSV download is the best route

### Geoscience Australia
- **URL:** https://www.ga.gov.au/scientific-topics/minerals
- **Data:** Australian mineral production, resources, reserves. Australia's Economic Demonstrated Resources (EDR)
- **Format:** PDF reports, Excel tables
- **Update frequency:** Annual (Australia's Identified Mineral Resources report)
- **Cost:** FREE
- **Coverage:** Australia only, all major minerals

### Natural Resources Canada (NRCan)
- **URL:** https://natural-resources.canada.ca/maps-tools-and-publications/publications/minerals-and-mining-publications/
- **Data:** Canadian mineral production statistics, trade, reserves
- **Format:** PDF, Excel
- **Update frequency:** Annual
- **Cost:** FREE

### European Commission — Critical Raw Materials
- **URL:** https://ec.europa.eu/growth/sectors/raw-materials/areas-specific-interest/critical-raw-materials_en
- **Data:** EU criticality assessments, supply risk analysis, EU production/import dependency
- **Format:** PDF reports, some Excel
- **Update frequency:** Every 3 years (criticality list); ad hoc studies
- **Cost:** FREE

### China Geological Survey / Ministry of Natural Resources
- **URL:** http://www.cgs.gov.cn/ (Chinese language)
- **Data:** China mineral production and reserves
- **Format:** Reports (Chinese), limited English
- **Cost:** FREE but access is limited; data often cited secondhand via USGS/BGS

---

## 2. Processing/Refining

### IEA Critical Minerals Data Explorer
- **URL:** https://www.iea.org/data-and-statistics/data-tools/critical-minerals-data-explorer
- **Data:** Demand projections, supply concentration, processing/refining shares by country for Li, Co, Ni, graphite, Cu, REE, Al
- **Format:** Interactive web tool, downloadable data (CSV/XLSX)
- **Update frequency:** Annual (aligned with Global Critical Minerals Outlook)
- **Cost:** FREE
- **Coverage:** Major critical minerals, global processing shares
- **Note:** Best free source for understanding refining concentration (e.g., China's share of cobalt refining)

### Benchmark Mineral Intelligence
- **URL:** https://www.benchmarkminerals.com/
- **Data:** Lithium, cobalt, nickel, graphite, rare earths — refinery capacity, planned projects, processing costs
- **Format:** Online platform, reports (PDF), data downloads
- **Cost:** **PAID** (subscriptions start ~$10K+/year)
- **Coverage:** Li-ion battery supply chain minerals

### CRU Group
- **URL:** https://www.crugroup.com/
- **Data:** Smelter/refinery capacity, production costs, supply/demand balances for base metals and specialty minerals
- **Format:** Online platform, Excel exports
- **Cost:** **PAID** (enterprise pricing)

### Wood Mackenzie
- **URL:** https://www.woodmac.com/
- **Data:** Processing capacity, cost curves, asset-level refinery data
- **Cost:** **PAID** (enterprise)

### Free Alternative: USGS Mineral Commodity Summaries
- Includes refinery production data for many commodities (e.g., rare earth oxide separation, lithium carbonate/hydroxide production by country)
- Not as granular as paid sources but covers major processors

---

## 3. Trade/Import-Export

### UN Comtrade
- **URL:** https://comtradeplus.un.org/
- **API:** https://comtradeapi.un.org/
- **Data:** Global bilateral trade data (imports/exports) by commodity HS code, reporter country, partner country
- **Format:** API (REST/JSON), bulk CSV downloads
- **Update frequency:** Monthly to annual depending on reporter; ~2-month lag
- **Cost:** FREE tier (100 calls/day, 10K records/call); premium for bulk access (~$600/yr for enhanced)
- **Coverage:** All countries reporting to UN, all HS codes
- **API access:**
  ```
  GET https://comtradeapi.un.org/data/v1/get/C/A/HS?reporterCode=842&period=2024&cmdCode=261510&flowCode=M
  ```
  - Requires free registration for API key
  - Rate limits: 100 requests/day (free), 500/day (premium)
- **Key HS codes for critical minerals:**

| Mineral | HS Code(s) | Description |
|---------|-----------|-------------|
| Lithium | 2836.91 | Lithium carbonate |
| Lithium | 2825.20 | Lithium oxide/hydroxide |
| Cobalt | 2605.00 | Cobalt ores and concentrates |
| Cobalt | 8105.20 | Cobalt mattes, unwrought |
| Rare Earths | 2846.10-90 | Rare earth compounds |
| Rare Earths | 2805.30 | Rare earth metals |
| Graphite | 2504.10-90 | Natural graphite |
| Nickel | 2604.00 | Nickel ores and concentrates |
| Nickel | 7502.10 | Unwrought nickel |
| Manganese | 2602.00 | Manganese ores |
| Tungsten | 2611.00 | Tungsten ores |
| Titanium | 2614.00 | Titanium ores (ilmenite, rutile) |
| Vanadium | 2615.90 | Vanadium ores |
| Antimony | 2617.10 | Antimony ores |
| Chromium | 2610.00 | Chromium ores |
| Tantalum | 2615.90 | Tantalum ores |
| Niobium | 2615.10 | Niobium ores |
| Gallium | 8112.92 | Gallium unwrought |
| Germanium | 8112.92 | Germanium unwrought |
| Indium | 8112.92 | Indium unwrought |
| Platinum Group | 7110.11-49 | Platinum, palladium, etc. |
| Beryllium | 8112.12 | Beryllium unwrought |
| Bismuth | 8106.10 | Bismuth unwrought |
| Tin | 2609.00 | Tin ores |

### US Census Bureau — USA Trade Online
- **URL:** https://usatrade.census.gov/
- **Data:** US imports/exports by HS code, port, country, monthly
- **Format:** Web query tool, CSV/Excel downloads
- **Update frequency:** Monthly (~2 month lag)
- **Cost:** FREE
- **Programmatic access:** No API; manual download or scrape. Can query by HS10 code for granularity beyond HS6

### ITC Trade Map
- **URL:** https://www.trademap.org/
- **Data:** Trade flows, market access, tariff data. Mirrors Comtrade with better UI
- **Format:** Web tool, limited CSV export
- **Update frequency:** Annual (mirrors Comtrade)
- **Cost:** FREE (limited access); full access for developing countries
- **Note:** Good for quick trade flow visualization; Comtrade API better for bulk programmatic use

### Eurostat COMEXT
- **URL:** https://ec.europa.eu/eurostat/web/international-trade-in-goods/data
- **Data:** EU member state trade at CN8 level (more granular than HS6)
- **Format:** Bulk download (CSV), API
- **Update frequency:** Monthly
- **Cost:** FREE

### China Customs (GACC)
- **URL:** http://www.customs.gov.cn/
- **Data:** Chinese import/export data
- **Format:** Reports, some data services
- **Cost:** Detailed data typically requires paid services (e.g., Global Trade Atlas, ImportGenius)

### Global Trade Atlas (S&P Global / IHS Markit)
- **URL:** https://www.spglobal.com/marketintelligence/en/mi/products/global-trade-atlas.html
- **Data:** Most comprehensive trade database — 100+ countries, HS10 level
- **Cost:** **PAID** (enterprise, ~$5K-20K/yr depending on coverage)

---

## 4. Pricing

### London Metal Exchange (LME)
- **URL:** https://www.lme.com/
- **Data:** Official daily settlement prices, cash/3-month forward, warehouse stocks for: Al, Cu, Ni, Zn, Sn, Pb, Co, Li (LME Lithium Hydroxide launched 2021)
- **Format:** Web display; bulk data via LME DataService (paid)
- **Update frequency:** Daily
- **Cost:** **PAID** for data feeds (LME DataService via Six Financial or direct). Delayed prices viewable on website for free
- **API:** Available through data vendors (Six, Refinitiv, Bloomberg)

### Shanghai Metals Market (SMM)
- **URL:** https://www.metal.com/
- **Data:** Chinese domestic prices for rare earths, lithium, cobalt, nickel, tungsten, antimony, gallium, germanium, indium, and many others
- **Format:** Web portal, Excel reports
- **Update frequency:** Daily
- **Cost:** **PAID** (subscriptions vary, ~$2K-10K/yr per commodity group); some spot prices visible for free
- **Note:** Essential for China-specific pricing; China dominates processing for many critical minerals

### Benchmark Mineral Intelligence
- **URL:** https://www.benchmarkminerals.com/
- **Data:** Lithium, cobalt, nickel, graphite, rare earth price assessments; battery-grade specific pricing
- **Format:** Reports, data portal
- **Cost:** **PAID** ($10K+/yr)

### Fastmarkets (formerly Metal Bulletin / Industrial Minerals)
- **URL:** https://www.fastmarkets.com/
- **Data:** Price assessments for minor metals, rare earths, lithium, cobalt, battery materials. Widely referenced in contracts
- **Format:** Data feeds (API available), web portal
- **Update frequency:** Daily to weekly depending on commodity
- **Cost:** **PAID** (enterprise pricing; individual commodity feeds available)

### Asian Metal
- **URL:** https://www.asianmetal.com/
- **Data:** Chinese and global prices for minor metals, rare earths, ferroalloys
- **Format:** Web, some free daily prices visible
- **Update frequency:** Daily
- **Cost:** Freemium — some prices visible; full data **PAID**

### Kitco (Precious Metals)
- **URL:** https://www.kitco.com/
- **Data:** Gold, silver, platinum, palladium spot prices
- **Format:** Web, RSS feeds
- **Cost:** FREE for spot prices
- **Programmatic:** Can scrape; no official free API

### FREE Pricing Alternatives

#### USGS Mineral Commodity Summaries
- Annual average prices for most minerals (not real-time, but good for historical trends)
- Free download as noted above

#### World Bank Commodity Price Data ("Pink Sheet")
- **URL:** https://www.worldbank.org/en/research/commodity-markets
- **Data:** Monthly prices for aluminum, copper, nickel, tin, zinc, iron ore, gold, silver, platinum, and more
- **Format:** Excel download (monthly updated)
- **Update frequency:** Monthly
- **Cost:** FREE
- **Download:** https://thedocs.worldbank.org/en/doc/5d903e848db1d1b83e0ec8f744e55570-0350012021/related/CMO-Historical-Data-Monthly.xlsx

#### Federal Reserve (FRED)
- **URL:** https://fred.stlouisfed.org/
- **Data:** Some commodity price series (aluminum, copper, nickel from World Bank/LME)
- **Format:** API (free, requires key), CSV, Excel
- **API:** `https://api.stlouisfed.org/fred/series/observations?series_id=PALUMUSDM&api_key=YOUR_KEY&file_type=json`
- **Cost:** FREE

#### Yahoo Finance / Google Finance
- Some metal futures prices available (copper, nickel, aluminum via CME/LME)
- Yahoo Finance API (unofficial): `yfinance` Python library
- **Cost:** FREE (unofficial, may break)

#### Quandl / Nasdaq Data Link
- **URL:** https://data.nasdaq.com/
- **Data:** Historical metal prices (LME, CME), some free datasets
- **Format:** API (REST/JSON/CSV)
- **Cost:** Free tier available; premium datasets paid
- **API:** `https://data.nasdaq.com/api/v3/datasets/LME/PR_NI?api_key=YOUR_KEY`

---

## 5. Company-Level Data

### S&P Global Market Intelligence (formerly SNL Metals & Mining)
- **URL:** https://www.spglobal.com/marketintelligence/en/campaigns/metals-mining
- **Data:** The gold standard — mine-level production, reserves, costs, ownership for 30K+ mining properties, 5K+ companies
- **Format:** Online platform, Excel/CSV exports, API
- **Cost:** **PAID** (enterprise, ~$20K-50K+/yr)
- **Coverage:** Global, all minerals

### Bloomberg Terminal
- **URL:** https://www.bloomberg.com/professional/
- **Data:** Company financials, production data, commodity prices, news
- **Cost:** **PAID** (~$24K/yr per terminal)

### Refinitiv Eikon (LSEG)
- **URL:** https://www.lseg.com/en/data-analytics
- **Data:** Mining company data, production, financials
- **Cost:** **PAID** (enterprise)

### SEC EDGAR (Free)
- **URL:** https://www.sec.gov/edgar/searchedgar/companysearch
- **Data:** Annual reports (10-K), quarterly reports (10-Q), 8-K filings for US-listed mining companies. Contains production volumes, reserves, costs
- **Format:** HTML, XBRL, full-text search
- **API:** https://efts.sec.gov/LATEST/search-index?q=%22critical+minerals%22&dateRange=custom&startdt=2024-01-01
  - Full-text search API: `https://efts.sec.gov/LATEST/search-index?q=QUERY`
  - XBRL API: `https://data.sec.gov/api/xbrl/companyfacts/CIK{number}.json`
- **Cost:** FREE
- **Tip:** Search for NI 43-101 technical reports (Canadian-listed) on SEDAR+ for detailed mine data

### SEDAR+ (Canadian filings)
- **URL:** https://www.sedarplus.ca/
- **Data:** Canadian mining company filings, NI 43-101 technical reports (detailed mine feasibility studies with reserves, production plans, costs)
- **Format:** PDF reports, searchable
- **Cost:** FREE

### Mining.com / Mining Intelligence
- **URL:** https://miningintelligence.com/
- **Data:** Mine rankings, top producers, basic production data
- **Format:** Web
- **Cost:** Freemium; detailed data **PAID**

### Free Alternative: InfoMine / Mining Data Online
- **URL:** https://www.miningdataonline.com/
- **Data:** Production data for individual mines compiled from public filings
- **Format:** Web tables
- **Cost:** FREE (limited data visible per mine)

### OpenCorporates
- **URL:** https://opencorporates.com/
- **Data:** Corporate ownership/subsidiary data — useful for tracing mining company structures
- **Format:** API available
- **Cost:** Free tier; bulk API access paid

---

## 6. Mine-Level Data

### USGS Mineral Resources Data System (MRDS)
- **URL:** https://mrdata.usgs.gov/mrds/
- **Data:** ~300K mineral deposit/occurrence records worldwide. Location (lat/lon), deposit type, commodity, development status, some production data
- **Format:** Web map, downloadable as shapefile, CSV, KML
- **Update frequency:** Irregular (legacy database, some updates)
- **Cost:** FREE
- **Programmatic access:**
  - WFS endpoint: `https://mrdata.usgs.gov/services/mrds?service=WFS&version=1.1.0&request=GetFeature&typeName=mrds`
  - Direct download: https://mrdata.usgs.gov/mrds/mrds-csv.zip
  - Map service: https://mrdata.usgs.gov/services/mrds (WMS/WFS)
- **Limitation:** Many records are historic; production data is sparse

### USGS Mineral Resources Online Spatial Data
- **URL:** https://mrdata.usgs.gov/
- **Data:** Collection of mineral resource databases including MRDS, ARDF (Alaska), deposit models
- **Format:** Shapefiles, WMS/WFS services, KML
- **Cost:** FREE

### S&P Global Mine Database
- (See Company-Level section)
- **Data:** Most comprehensive: 35K+ properties with production, reserves, ownership, stage, coordinates
- **Cost:** **PAID**

### Mindat.org
- **URL:** https://www.mindat.org/
- **Data:** ~400K locality records, mineralogical data, mine locations, photos. Community-maintained
- **Format:** Web, API available
- **API:** https://api.mindat.org/ (free with registration, rate limited)
- **Cost:** FREE
- **Note:** More mineralogical than economic, but excellent for deposit locations

### OpenStreetMap (Mining features)
- **URL:** https://www.openstreetmap.org/
- **Data:** Many mines tagged with `landuse=quarry` or `man_made=mineshaft`
- **Format:** Overpass API queries
- **Programmatic access:**
  ```
  [out:json];node["landuse"="quarry"];out body;
  ```
  Via: https://overpass-api.de/api/interpreter
- **Cost:** FREE

### Global Energy Monitor — Global Coal Mine Tracker / Global Steel Plant Tracker
- **URL:** https://globalenergymonitor.org/
- **Data:** Individual mine/plant tracking for coal, steel, and increasingly other minerals
- **Format:** Downloadable spreadsheets, wiki-style pages
- **Cost:** FREE
- **Note:** Expanding to critical minerals

### Cobalt Institute — Mine Map
- **URL:** https://www.cobaltinstitute.org/
- **Data:** Cobalt mine locations and producers
- **Cost:** Some data free

---

## 7. Supply Chain / Downstream

### IEA Critical Minerals Data Explorer
- (See Processing section above)
- **Data:** Demand projections by technology (EVs, wind, solar, batteries), supply/demand balances
- **Cost:** FREE

### DOE Critical Materials Assessment
- **URL:** https://www.energy.gov/eere/solar/critical-materials-assessment
- **Data:** US DOE assessment of supply chain risks, demand forecasts for clean energy minerals
- **Format:** PDF reports
- **Cost:** FREE

### Argonne National Laboratory — GREET Model
- **URL:** https://greet.anl.gov/
- **Data:** Life-cycle analysis including material inputs for energy technologies — helps understand demand drivers
- **Format:** Downloadable software + data
- **Cost:** FREE

### International Aluminium Institute
- **URL:** https://international-aluminium.org/statistics/
- **Data:** Primary aluminium production, energy use, recycling rates by region
- **Format:** Excel downloads
- **Cost:** FREE

### Cobalt Institute
- **URL:** https://www.cobaltinstitute.org/
- **Data:** Cobalt demand by end-use sector (batteries, superalloys, etc.)
- **Format:** Reports (PDF)
- **Cost:** Some free, detailed reports paid

### International Copper Study Group (ICSG)
- **URL:** https://icsg.org/
- **Data:** Copper supply/demand, consumption by sector
- **Cost:** **PAID** for detailed data

### International Nickel Study Group (INSG)
- **URL:** https://insg.org/
- **Data:** Nickel supply/demand balances
- **Cost:** **PAID** for detailed data

### International Lead and Zinc Study Group (ILZSG)
- **URL:** https://www.ilzsg.org/
- **Cost:** **PAID**

### Battery supply chain specifically:
- **Benchmark Mineral Intelligence** (PAID) — most detailed
- **BloombergNEF** (PAID) — extensive battery/EV supply chain data
- **IEA Global EV Outlook** (FREE) — https://www.iea.org/reports/global-ev-outlook-2025 — annual report with battery mineral demand data

---

## 8. Defense-Specific

### DLA Strategic Materials (formerly Defense National Stockpile)
- **URL:** https://www.dla.mil/Strategic-Materials/
- **Data:** US National Defense Stockpile inventory levels, authorized disposals, acquisition targets
- **Format:** PDF reports, annual materials plan (AMP)
- **Update frequency:** Annual (Annual Materials Plan)
- **Cost:** FREE
- **Key document:** Annual Materials Plan to Congress
- **Programmatic:** Manual download; limited machine-readable data

### USGS — Critical Minerals List
- **URL:** https://www.usgs.gov/news/national-news-release/us-geological-survey-releases-2022-list-critical-minerals
- **Data:** Official US list of critical minerals (50 minerals as of 2022 update)
- **Cost:** FREE

### Defense Minerals Exploration Activities (DMEA) — Historical
- Predecessor to current DLA programs. Historical reports available via USGS archives
- **URL:** https://pubs.usgs.gov/ (search DMEA)

### DOD Industrial Base Reports
- **URL:** https://www.businessdefense.gov/
- **Data:** Reports on industrial base vulnerabilities including mineral supply chains
- **Format:** PDF
- **Cost:** FREE (when publicly released)

### Executive Orders and Policy Documents
- **EO 13817 (2017)** and **EO 14017 (2021)** — Supply chain reviews including critical minerals
- **100-Day Supply Chain Review** (2021): https://www.whitehouse.gov/wp-content/uploads/2021/06/100-day-supply-chain-review-report.pdf
- **Cost:** FREE

### Congressional Research Service (CRS) Reports
- **URL:** https://crsreports.congress.gov/
- **Data:** Excellent policy-oriented summaries of critical mineral issues, stockpile status
- **Format:** PDF
- **Cost:** FREE
- **Tip:** Search for "critical minerals" — regularly updated reports

---

## 9. Real-Time / Near-Real-Time Feeds

### True real-time mineral data is extremely limited. Best options:

#### LME (via data vendors)
- Real-time/15-min delayed prices for LME-traded metals (Al, Cu, Ni, Zn, Sn, Pb, Co, Li)
- **Access via:** Bloomberg, Refinitiv, Six Financial, or LME DataService
- **Cost:** **PAID**

#### CME Group (COMEX)
- **URL:** https://www.cmegroup.com/
- **Data:** Futures for copper, gold, silver, platinum, palladium
- **Format:** Market data feeds
- **Cost:** **PAID** for real-time; delayed quotes free on website

#### Yahoo Finance / yfinance (Python)
- Delayed (15-20 min) futures prices for CME/LME metals
- ```python
  import yfinance as yf
  copper = yf.Ticker("HG=F")  # Copper futures
  nickel = yf.Ticker("^NICK")  # Nickel
  ```
- **Cost:** FREE (unofficial)

#### Metals API
- **URL:** https://metals-api.com/
- **Data:** Spot prices for precious metals + some base metals
- **Format:** REST API (JSON)
- **Cost:** Free tier (50 requests/month); paid tiers from $10/mo
- **API:** `https://metals-api.com/api/latest?access_key=KEY&base=USD&symbols=XAU,XAG,XPT,XPD`

#### MetalpriceAPI
- **URL:** https://metalpriceapi.com/
- **Data:** Similar to above — precious metals and some base metals
- **Format:** REST API
- **Cost:** Free tier (100 requests/month); paid from $10/mo

#### Twelve Data
- **URL:** https://twelvedata.com/
- **Data:** Commodity prices including some metals
- **Format:** REST API, WebSocket
- **Cost:** Free tier; paid for more

### Bottom line on real-time:
- Precious metals (Au, Ag, Pt, Pd): fairly accessible via free/cheap APIs
- Base metals (Cu, Ni, Al, Zn): available via LME delayed or futures
- Specialty/critical minerals (Li, Co, REE, Ga, Ge): **NO real-time feeds exist**. Pricing is assessed weekly/monthly by agencies (Fastmarkets, Benchmark, Asian Metal). This is a market gap.

---

## 10. Geospatial

### USGS Mineral Resources Online Spatial Data
- **URL:** https://mrdata.usgs.gov/
- **Data:** MRDS mine locations, mineral deposit models, geophysical/geochemical data
- **Format:** WMS, WFS, shapefiles, KML
- **Cost:** FREE
- **WFS:** `https://mrdata.usgs.gov/services/mrds?service=WFS&request=GetCapabilities`

### USGS Earth Explorer
- **URL:** https://earthexplorer.usgs.gov/
- **Data:** Satellite imagery useful for monitoring mine sites (Landsat, Sentinel)
- **Format:** GeoTIFF
- **Cost:** FREE

### Global Mining Footprint (via satellite)
- Maus et al. (2020) dataset: ~44K mining areas globally mapped from satellite
- **URL:** https://doi.org/10.1594/PANGAEA.910894
- **Data:** Polygons of global mining areas
- **Format:** Shapefile/GeoPackage
- **Cost:** FREE

### Natural Earth
- **URL:** https://www.naturalearthdata.com/
- **Data:** Global vector data (ports, railways, roads) — useful for supply chain routing
- **Format:** Shapefile
- **Cost:** FREE

### Marine Traffic / VesselFinder (Shipping)
- **URL:** https://www.marinetraffic.com/ / https://www.vesselfinder.com/
- **Data:** Real-time vessel tracking (AIS data) — track bulk carrier movements from mining ports
- **Format:** API available
- **Cost:** Free for basic vessel lookup; API **PAID** ($500+/mo for bulk)

### Global Ports Data
- **World Port Index:** https://msi.nga.mil/Publications/WPI
- **Data:** 3,600+ port locations with capabilities
- **Format:** Downloadable database
- **Cost:** FREE

### OpenStreetMap + Overpass API
- Query mining infrastructure globally
- **Cost:** FREE
- **Example query for mines:**
  ```
  [out:json][timeout:60];
  (
    node["man_made"="mineshaft"];
    way["landuse"="quarry"];
    node["industrial"="mine"];
  );
  out body;
  ```

### Google Earth Engine
- **URL:** https://earthengine.google.com/
- **Data:** Satellite imagery time series for monitoring mine expansion, tailings, infrastructure
- **Cost:** FREE for research; commercial use requires license

---

## Summary Matrix: Best Free Sources by Category

| Category | Best Free Source | Programmatic? |
|----------|----------------|---------------|
| Production | USGS NMIC + BGS | XLSX/CSV download |
| Processing | IEA Critical Minerals Explorer | Web download |
| Trade | UN Comtrade API | REST API (100 calls/day free) |
| Pricing | World Bank Pink Sheet + FRED | Excel + API |
| Company | SEC EDGAR + SEDAR+ | API (EDGAR) + web (SEDAR) |
| Mine locations | USGS MRDS | WFS + CSV download |
| Supply chain | IEA + DOE reports | PDF/web |
| Defense | DLA + CRS reports | PDF |
| Real-time prices | Yahoo Finance (yfinance) | Python library |
| Geospatial | USGS mrdata + PANGAEA mining footprint | WFS + shapefile |

---

## Recommended Stack for a Free/Low-Cost Data Product

1. **Production data pipeline:** Scrape USGS Commodity Summaries XLSX + BGS CSV annually
2. **Trade data pipeline:** UN Comtrade API (free tier, batch overnight) — pull by HS code for all critical mineral codes
3. **Pricing pipeline:** World Bank monthly + FRED API for major metals; Yahoo Finance for daily futures (Cu, Ni, Al)
4. **Mine database:** USGS MRDS (bulk CSV) + Mindat API for enrichment
5. **Company data:** SEC EDGAR full-text search API for mining company filings
6. **Geospatial:** MRDS WFS + Maus et al. mining footprint dataset
7. **Supply chain context:** IEA data explorer + DOE reports (manual annual update)

**For premium depth, the top paid sources to consider (in priority order):**
1. S&P Global Market Intelligence (~$30K/yr) — mine-level data, the backbone of industry
2. Fastmarkets or Benchmark (~$10K/yr) — essential for minor/specialty mineral pricing
3. UN Comtrade premium ($600/yr) — lift API rate limits
4. Shanghai Metals Market (~$5K/yr) — Chinese market pricing

---

## Appendix: Critical Minerals List (US, 2022)

Aluminum, antimony, arsenic, barite, beryllium, bismuth, cerium, cesium, chromium, cobalt, dysprosium, erbium, europium, fluorspar, gadolinium, gallium, germanium, graphite, hafnium, holmium, indium, iridium, lanthanum, lithium, lutetium, magnesium, manganese, neodymium, nickel, niobium, palladium, platinum, praseodymium, rhodium, rubidium, ruthenium, samarium, scandium, tantalum, tellurium, terbium, thallium, tin, titanium, tungsten, vanadium, ytterbium, yttrium, zinc, zirconium.
