# The COVID Tracking Project Racial Tracker

[The COVID Tracking Project](https://covidtracking.com/race) is a volunteer organization launched from The Atlantic dedicated to collecting and publishing the data required to understand the COVID-19 outbreak in the United States.

Every day, the Tracking Project volunteers collect official data on COVID-19 testing and patient outcomes from all 50 states, 5 territories, and the District of Columbia. The dataset is currently in use by national and local news organizations across the United States, and by research projects and agencies worldwide. Its data API receives about two million requests per day. Read the [methodology](https://covidtracking.com/about-data/sources).

More recently, The COVID Tracking Project has also been collecting race and ethnicity data in association with known cases to better understand vulnerability in the United States. 


## Dataset 

The COVID Tracking Project offers a separate dataset containing racial and ethnicity data. It features the number of known **positive cases**, **negative cases**, and **deaths** associated with each race and ethnicity, including white, black, Asian, Latinx, multiracial, etc.

Apart from the racial dataset, the Tracking Project also features daily and historical case counts by state, region, and country-wide total. See the [complete dataset](https://covidtracking.com/data) and their [APIs](https://covidtracking.com/data/api).

Data is updated every day, and is available back till _April 12th, 2020_.


## Accessing Data

You can view the racial data dashboard on [The COVID Tracking Project website](https://covidtracking.com/race/dashboard) for summary and analysis.

Live data entry is available as a Google Sheets [spreadsheet](https://docs.google.com/spreadsheets/u/1/d/e/2PACX-1vR_xmYt4ACPDZCDJcY12kCiMiH0ODyx3E1ZvgOHB8ae1tRcjXbs_yWBOA4j4uoCEADVfC1PS2jYO68B/pubhtml#). 

Alternatively, download the `.csv` file from the [website](https://covidtracking.com/race/about#download-the-data) or find it in the [`dataset`](dataset/) directory. Last updated _July 27th, 2020_.

## Structure

The racial dataset is organized in a time-series format where data for each state on a day is stored in a row.

### Field Description

| Field | Description | Type | Example |
|-|-|-|-|
| `Date` | Date on which the data was collected, in the format `YYYYMMDD` | string | 20200729 |
| `State` | [2-letter abbreviation](https://www.ssa.gov/international/coc-docs/states.html) representing the state in which data was collected | string | AL |
| `Cases_Total` | Total number of cases for the specified day | integer | 83782 |
| `Cases_White` | Total number of White cases for the specified day | integer | 25915 |
| `Cases_Black` | Total number of Black cases for the specified day | integer | 23239 |
| `Cases_LatinX` | Total number of Latinx cases for the specified day | integer | 38887 |
| `Cases_Asian` | Total number of Asian cases for the specified day | integer | 309 |
| `Cases_AIAN` | Total number of Native American ([AIAN](https://en.wikipedia.org/wiki/AIAN_(U.S._Census))) cases for the specified day | integer | 120 |
| `Cases_NHPI` | Total number of Native Hawaiian and Pacific Islanders ([NHPI](https://www.census.gov/newsroom/press-kits/2019/nhpi.html)) cases for the specified day | integer | 2103 |
| `Cases_Multiracial` | Total number of multiracial cases for the specified day | integer | 2305 |
| `Cases_Other` | Total number of cases from other races for the specified day | integer | 5456 |
| `Cases_Unknown` | Total number of cases from an unknown race for the specified day | integer | 3502 |
| `Cases_Ethnicity_Hispanic` | Total number of Hispanic cases for the specified day | integer | 9493 |
| `Cases_Ethnicity_NonHispanic` | Total number of non-Hispanic cases for the specified day | integer | 31475 |
| `Cases_Ethnicity_Unknown` | Total number of cases from an unknown ethnicity for the specified day | integer | 0 |
| `Deaths_Total` | Total number of deaths for the specified day | integer | 434 |
| `Deaths_White` | Total number of White deaths for the specified day | integer | 255 |
| `Deaths_Black` | Total number of Black deaths for the specified day | integer | 113 |
| `Deaths_LatinX` | Total number of Latinx deaths for the specified day | integer | 946 |
| `Deaths_Asian` | Total number of Asian deaths for the specified day | integer | 6 |
| `Deaths_AIAN` | Total number of Native American ([AIAN](https://en.wikipedia.org/wiki/AIAN_(U.S._Census))) deaths for the specified day | integer | 2 |
| `Deaths_NHPI` | Total number of Native Hawaiian and Pacific Islanders ([NHPI](https://www.census.gov/newsroom/press-kits/2019/nhpi.html)) deaths for the specified day | integer | 31 |
| `Deaths_Multiracial` | Total number of multiracial deaths for the specified day | integer | 46 |
| `Deaths_Other` | Total number of deaths from other races for the specified day | integer | 30 |
| `Deaths_Unknown` | Total number of deaths from an unknown race for the specified day | integer | 0 |
| `Deaths_Ethnicity_Hispanic` | Total number of Hispanic deaths for the specified day | integer | 43 |
| `Deaths_Ethnicity_NonHispanic` | Total number of non-Hispanic deaths for the specified day | integer | 394 |
| `Deaths_Ethnicity_Unknown` | Total number of deaths from an unknown ethnicity for the specified day | integer | 0 |

**Note**: Fields may be empty.

## Attribution

The COVID Tracking Project data is published under a [Creative Commons CC BY-NC-4.0](http://creativecommons.org/licenses/by-nc/4.0/) license, which requires users to attribute the source and license type (CC BY-NC-4.0) when sharing our data or website content.
