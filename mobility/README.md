## Source Index
This directory contains dataset from the sources below. For more descriptions, click on the link to each source.

| Source | Description | Tags | Granularity | Compr-ness* | Source Type | Last Updated |
|-|-|-|-|-|-|-|
| [Jataware](https://github.com/jataware/covid-19-data) | Machine-curated data on NPI and healthcare capacity at city, county, state and country level. | `NPI`, `Capacity` | County, State, Country | General | Aggregate | - |
| [Google](https://www.google.com/covid19/mobility/) | Mobility trends for visits to workplaces, retail stores, parks, etc., compared to a baseline pre-COVID. | `Traffic`, `Visits`, `Trends` | County, State, Country | General | Aggregate | 05/25/2020 |
| [Oxford](https://github.com/OxCGRT/covid-policy-tracker) | Comprehensive dataset on the record of government policies enacted to limit COVID-19 spread at a country level, indexed in terms of overall response, containment measures, stringency and economic support. | `NPI`, `Index` | Country | Compr. | Official | - |
| [University of Washington](https://github.com/COVID19StatePolicy/SocialDistancing) | State-level responses to contain COVID-19 spread in the US. | `NPI` | State | Compr. | Official | - |
| [WSDOT](https://tracflow.wsdot.wa.gov/contourdata/brainscan) | Volume of traffic per hour along highways around Washington state from Jan 1 to Jun 1. | `Traffic` | Washington | General | Official | 06/01/2020 |
| [Yahoo! Japan](https://ds.yahoo.co.jp/report/) | Index of the # of people visiting and leaving each prefecture in Japan each day and month in 2020 as compared to 2019. | `Traffic`, `Index` | Japan | General | Aggregate | 06/01/2020 |
| [Descartes Labs](https://github.com/descarteslabs/DL-COVID-19) | Dataset of the distance a typical member of a given population moves in a day. | `Travel Distance` | County, State | General | Aggregate | - |
| [USDOT](https://datahub.transportation.gov/Research-and-Statistics/Monthly-Transportation-Statistics/crem-w557) | Full monthly transportation statistics across the federal government. | `Traffic`, `Travel Distance`, `Economic` | United States | Compr. | Official | 06/03/2020 |
| [Baidu](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/FAEZIO&version=16.1) | Percentage change in # of people entering and leaving a city in China. | `Traffic`, `Trends`, `Index` | China | General | Aggregate | 05/03/2020 |
| [Facebook](https://dataforgood.fb.com/) | Travel patterns and movement index across the United States. | `Traffic`, `Trends`, `Index` | County, State, Country | General | Aggregate | 06/03/2020 |
| [Apple](https://www.apple.com/covid19/mobility) | Relative volume of directions requests per region as compared to baseline on Jan 13th, 2020. | `Traffic`, `Trends` | County, State, Country | General | Aggregate | 06/02/2020 |
| [UC Berkeley](https://covidvis.berkeley.edu/) | Dataset for visualizing the impact of NPIs, more comprehensive than Keystone's or Stanford's. | `NPI`, `Cases` | County, State, Country | Compr. | Aggregate | - |

## Metadata Descriptions
- Compr-ness*: Comprehensiveness
- `Official`: data officially reported by authorities
- `Aggregate`: data curated from various sources, but not officially reported by authorities
- `Comprehensive`: data reported is comprehensive and contains low-level details
- `General`: data reported is not comprehensive and is meant for a high-level overview

## Tag Descriptions
- `Trends`: trends (% change) data
- `Index`: contains indexing/ranking mechanism
- `NPI`: related to [non-pharmaceutical interventions](https://www.cdc.gov/nonpharmaceutical-interventions/index.html) implemented
- `Capacity`: related to healthcare support facility, such as # of beds, ventilators, etc.
- `Cases`: contains information about positive cases and deaths
- `Economic`: contains economic data, e.g. government spending, tax relief
- `Visits`: related to the # of visits to a particular venue
- `Traffic`: related to large-scale vehicular or pedestrian traffic flow, e.g. volume or patterns
- `Travel Distance`: related to the travel distance of the population
- `Infrastructure`: contains information about infrastructure that eases or restricts mobility
- `Population Density`: contains information about population density

## Additional sources pending response
- SafeGraph
- Cuebiq
- Streetlight
- INRIX
- Camber Systems (pending Data Use Agreement)
- Unacast
- University of Maryland's Maryland Transportation Institute
- Keystone
