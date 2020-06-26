# Google Community Mobility Reports

Google is [publishing datasets](https://www.google.com/covid19/mobility/) that provide insights into what has changed in response to policies aimed at combating COVID-19. The reports chart movement trends over time by geography, across different categories of places such as retail and recreation, groceries and pharmacies, parks, transit stations, workplaces, and residential.

These metrics are sourced from users who have enabled location history on their Google Account — same data used to show [popular times](https://support.google.com/business/answer/6263531?hl=en) for places in Google Maps. 


## Datasets

[Google Community Mobility Reports](https://www.google.com/covid19/mobility/) are availble for different countries (and in the United States, for every state).

It contains mobility trends for the following places:

- **Grocery & pharmacy** such as grocery markets, food warehouses, farmers markets, specialty food shops, drug stores, and pharmacies
- **Parks** such as local parks, national parks, public beaches, marinas, dog parks, plazas, and public gardens
- **Transit stations** including public transport hubs such as subway, bus, and train stations 
- **Retail & recreation** such as restaurants, cafes, shopping centers, theme parks, museums, libraries, and movie theaters
- **Residential**: places of residence
- **Workplaces**: offices and places of work

According to [Google's documentation](https://www.google.com/covid19/mobility/data_documentation.html?hl=en): 

> These datasets show how visits and length of stay at different places change compared to a baseline. 
> 
> Changes for each day are compared to a baseline value for that day of the week:
> - The baseline is the median value, for the corresponding day of the week, during the 5-week period Jan 3–Feb 6, 2020
> - The datasets show trends over several months with the most recent data representing approximately 2-3 days ago — this is how long it takes to produce the datasets

Please read the [help section](https://support.google.com/covid19-mobility?hl=en#topic=9822927) to understand how to interpret the mobility data.

Google Community Mobility Reports is updated every week, and is available back till _February 15th, 2020_.


## How to access data

You can download the global `.csv` file used to generate every report on the [Google Mobility Reports website](https://www.google.com/covid19/mobility/), at this [download link](https://www.gstatic.com/covid19/mobility/Global_Mobility_Report.csv) or find it in the [`dataset`](dataset/) directory (28.5 MB). Last updated _May 25th, 2020_. 


## Structure

The `.csv` file contains the following fields: 

| Field | Description | Type | Example |
|-|-|-|-|
| `country_region_code` | [ISO-2 code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) representing the country in which data was collected | string | AE |
| `country_region` | Name of the country in which data was collected | string | United Arab Emirates |
| `sub_region_1` | Name of the first [administrative unit]. Represents states in the US. | string | Abu Dhabi |
| `sub_region_2` | Name of the second [administrative unit], usually empty. Represents county in the US. | string | Autauga County |
| `date` | Date on which data was collected | string | 2/15/2020 |
| `retail_and_recreation_percent_change_from_baseline` | Percentage change of mobility to places for retail and recreation as compared to baseline | integer | 0 |
| `grocery_and_pharmacy_percent_change_from_baseline` | Percentage change of mobility to places for grocery and pharmacy as compared to baseline | integer | 4 |
| `parks_percent_change_from_baseline` | Percentage change of mobility to parks as compared to baseline | integer | 5 |
| `transit_stations_percent_change_from_baseline` | Percentage change of mobility to transit stations as compared to baseline | integer | 0 |
| `workplaces_percent_change_from_baseline` | Percentage change of mobility to workplaces as compared to baseline | integer | 2 |
| `residential_percent_change_from_baseline` | Percentage change of mobility to residential places as compared to baseline | integer | 1 |

**Note**: fields can be empty.

[administrative unit]: https://en.wikipedia.org/wiki/Administrative_division#:~:text=For%20clarity%20and%20convenience%20the,or%20%22second%20administrative%20level%22.

## Attribution

If you publish results based on this data set, please cite as:

> Google LLC _"Google COVID-19 Community Mobility Reports"_.
> https://www.google.com/covid19/mobility/ Accessed: \<date\>.
