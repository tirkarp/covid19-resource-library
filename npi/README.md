# Non-pharmaceutical Interventions and Mobility Infrastructure

[Non-pharmaceutical Interventions (NPIs)](https://www.cdc.gov/nonpharmaceutical-interventions/index.html) are measures apart from healthcare interventions like getting vaccinated or taking medicine, that helps slow the spread of illnesses. 

This directory contains datasets related to NPIs implemented by authorities at multiple levels, as well as infrastructure that is put in place to help facilitate or slow down the population mobility.

## Source Index
This directory contains dataset from the sources below. For more descriptions, click on the link to each source.

| Source | Description | Tags | Granularity | Compr-ness* | Source Type | First Updated | Last Updated |
|-|-|-|-|-|-|-|
| [Jataware](https://github.com/jataware/covid-19-data) | Machine-curated data on NPI and healthcare capacity at city, county, state and country level. | `NPI`, `Capacity` | County, State, Country | General | Aggregate | - | - |
| [Oxford](https://github.com/OxCGRT/covid-policy-tracker) | Comprehensive dataset on the record of government policies enacted to limit COVID-19 spread at a country level, indexed in terms of overall response, containment measures, stringency and economic support. | `NPI`, `Index` | Country | Compr. | Official | - | - |
| [University of Washington](https://github.com/COVID19StatePolicy/SocialDistancing) | State-level responses to contain COVID-19 spread in the US. | `NPI` | State | Compr. | Official | - | - |
| [UC Berkeley](https://covidvis.berkeley.edu/) | Dataset for visualizing the impact of NPIs, more comprehensive than Keystone's or Stanford's. | `NPI` | County, State, Country | Compr. | Aggregate | - | - |
| [IOM Point-of-Entry Restriction](https://data.humdata.org/dataset/country-point-of-entry-mobility-restriction-covid-19-iom-dtm) | Dataset for restrictions on point-of-entry at a country level. | `NPI`, `Infra.` | City, Country | Compr. | Aggregate | - | 05/28/2020 |

## Metadata Descriptions
- Compr-ness*: Comprehensiveness
- `Official`: data officially reported by authorities
- `Aggregate`: data curated from various sources, which may not have been officially reported by authorities
- `Comprehensive`: data reported is comprehensive and contains low-level details
- `General`: data reported is not comprehensive and is meant for a high-level overview

## Tag Descriptions
- `Trends`: trends (% change) data
- `Index`: contains indexing/ranking mechanism
- `NPI`: related to [non-pharmaceutical interventions](https://www.cdc.gov/nonpharmaceutical-interventions/index.html) implemented
- `Capacity`: related to healthcare support facility, such as # of beds, ventilators, etc.
- `Cases`: contains information about positive cases and deaths
- `Economic`: contains economic data, e.g. government spending, tax relief
- `Infra.`: contains information about infrastructure that eases or restricts mobility

## Additional Sources

Sources we would like to add, but lack the resources to do so. Contributions are welcome.

- [CoronaNet](https://github.com/saudiwin/corona_tscs)
