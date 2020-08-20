# Testing

This directory contains datasets related to COVID-19 testing and results, including positive cases, negative cases, fatality, testing rate.

## Source Index

For more descriptions, click on the link to each source.

| Source | Description | Tags | Granularity | Compr-ness* | Source Type | First Updated | Last Updated |
|-|-|-|-|-|-|-|-|
| [John Hopkins](jhu/) | Centralized repository of cases around the world | `Cases` | City, County, State, Country, Worldwide | General | Aggregate | 01/22/2020 | - |
| [New York Times](nytimes/) | Cases, deaths, excess deaths, mask usage from official figures | `Cases`, `Excess` | County, State, Country | General | Aggregate | 01/21/2020 | - |
| [Our World in Data](owid/) | Detailed case counts and metadata associated with each country | `Cases`, `Testing`, `Infra.`, `Medical`, `Economic`, `Demographics` | Country | Compr. | Aggregate | 03/13/2020 | - |
| [COVID Tracking Project](covid-tracking-project/) | Detailed case counts compiled from official sources in each state | `Cases`, `Testing`, `Infra.`, `Demographics` | State | Compr. | Official | 01/22/2020 | - |
| [CDC](cdc/) | Weekly deaths and excess deaths | `Deaths`, `Excess` | State | Compr. | Official | 01/14/2020 | 08/01/2020 |
| [European CDC](ecdc/) | Daily case counts, testing volumes and hospital admission rates | `Cases`, `Testing`, `Admission` | Country | General | Official | 01/01/2020 | 08/16/2020 |


## Field Description
- Compr-ness*: Comprehensiveness
- `Official`: data officially reported by authorities
- `Aggregate`: data curated from various sources, which may not have been officially reported by authorities

## Additional Sources 

- WHO
- USA Facts
- Corona Data Scraper
- Covid Care Map
- testandtrace.com
