# Centers for Disease Control and Prevention (CDC)'s Vulnerability Data

CDC centralizes reporting data from nearly every state and related government agencies to form official figures for deaths, vulnerability, and disparities. 

Data is usually aggregated through multiple official data sources, collected through surveys, hospital surveillance, official county-level and state-level figures, U.S. Census Bureau, and third-party organizations. CDC is providing the most recent data available on deaths, mental health, and access to health care, loss of work due to illness, and telemedicine.

## Datasets

Among CDC's various datasets, two of them can be used to extract general death information:

- [**NCHS Daily Updates**](#nchs-daily-updates): daily update of provisional death count in the US
- [**Excess Deaths**](#excess-deaths): difference between actual vs. expected death count in a time period

More datasets from the CDC can be found on the [CDC website](https://www.cdc.gov/coronavirus/2019-ncov/cases-updates/index.html) and [NCHS website](https://www.cdc.gov/nchs/covid19/index.htm). Note that death count from other factors unrelated to COVID-19, both during and before the pandemic is also available.

**Note**: COVID-19 death counts shown here may differ from other published sources, as data currently are lagged by an average of 1–2 weeks.

## Accessing Data

All datasets are downloaded into the [`dataset/`](dataset/) directory for easier access. Last updated _August 13th, 2020_.

Visualization, analysis and more recent datasets are available on the [CDC's website](https://www.cdc.gov/nchs/covid19/index.htm) and [NCHS website](https://www.cdc.gov/nchs/covid19/index.htm)

## [NCHS Daily Updates](https://www.cdc.gov/nchs/nvss/vsrr/COVID19/index.htm)

[NCHS Daily Updates](https://www.cdc.gov/nchs/nvss/vsrr/COVID19/index.htm) present the weekly **provisional count of deaths** in the United States due to COVID-19, including deaths from the following causes:

- **deaths from all causes and percent of expected deaths** (based on previous years)
- **pneumonia deaths** (excluding pneumonia deaths involving influenza)
- pneumonia deaths involving COVID-19
- **influenza deaths**, and deaths involving pneumonia 
- influenza
- **COVID-19**

Even though the data represents the weekly count, it is updated daily, and is available back till _February 2nd, 2020_.

### Structure

NCHS Daily Updates data is included in the file [`daily-update.csv`](dataset/daily-update.csv).

#### Field Description

| Field | Description | Type | Example |
|-|-|-|-|
| `Data as of` | Date on which data was last updated, in the format `M/D/YYYY` | string | 3/1/2020 |
| `Start week` | Starting week as indicated by `Indicator`, in the format `M/D/YYYY`. May be the same as `End Week`. | string | 2/1/2020 |
| `End Week` | Ending week as indicated by `Indicator`, in the format `M/D/YYYY`. May be the same as `Start week`. | string | 2/1/2020 |
| `Group` | How data is grouped, as indicated by `Indicator` | string | By week |
| `State` | State in which the data was recorded. The value `United States` here represents the country-wide total. | string | Alabama |
| `Indicator` | Indicator as to how data is to be interpreted | string | Week-ending |
| `COVID-19 Deaths` | Total COVID-19 deaths during the time period represented | integer | 17021 |
| `Total Deaths` | Total deaths from all causes during the time period represented | integer | 76373 |
| `Percent of Expected Deaths` | Number of deaths for all causes for this week in 2020 compared to the average number across the same week in 2017–2019 | float | 1.41 |
| `Pneumonia Deaths` | Total deaths from pneumonia, with and without COVID-19 but excluding influenza, during the time period represented | integer | 75 |
| `Pneumonia and COVID-19 Deaths` | Total deaths from pneumonia with COVID-19 but excluding influenza, during the time period represented | integer | 16 |
| `Influenza Deaths` | Total deaths from influenza, with and without COVID-19 or pneumonia, during the time period represented | integer | 13 |
| `Pneumonia, Influenza, or COVID-19 Deaths` | Total deaths from pneumonia, with COVID-19 and influenza, during the time period represented | integer | 143 |
| `Footnote` | Additional information regarding the data represented | string |  |

**Note**: Fields may be empty. Please also read the [notes from the official documentaion](https://www.cdc.gov/nchs/nvss/vsrr/COVID19/index.htm).

## [Excess Deaths](https://www.cdc.gov/nchs/nvss/vsrr/covid19/excess_deaths.htm)

[Excess Deaths](https://www.cdc.gov/nchs/nvss/vsrr/covid19/excess_deaths.htm) can provide information about the burden of mortality potentially related to the COVID-19 pandemic, including deaths that are directly or indirectly attributed to COVID-19. 

Excess deaths are typically defined as the **difference between the observed numbers of deaths in specific time periods and expected numbers of deaths in the same time periods**. This visualization provides weekly estimates of excess deaths by the jurisdiction in which the death occurred. **Weekly counts of deaths are compared with historical trends** to determine whether the number of deaths is significantly higher than expected.

Read the official [methodology](https://www.cdc.gov/nchs/nvss/vsrr/covid19/excess_deaths.htm).

### Structure

See the [official documentation](https://www.cdc.gov/nchs/nvss/vsrr/covid19/excess_deaths.htm).

## Attribution

No attribution information is available on CDC's website.
