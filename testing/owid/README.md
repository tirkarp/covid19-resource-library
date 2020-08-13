# Our World in Data COVID-19 Data

[Our World in Data (OWID)](https://ourworldindata.org/about) is a project of the [Global Change Data Lab](https://global-change-data-lab.org/), an educational charity based in Oxford, UK. Its mission is to publish research and data to make progress against the world’s largest problems.

OWID has curated [datasets](https://ourworldindata.org/coronavirus) that answers how COVID-19 pandemic is spreading, what impact the pandemic has, how we can make progress against the pandemic, and whether the measures countries are taking are successful or not. 

Data is sourced from multiple places, most notably the [European Centre for Disease Prevention and Control (ECDC)](https://www.ecdc.europa.eu/en/publications-data/download-todays-data-geographic-distribution-covid-19-cases-worldwide), country-by-country official figures, and institutions like the World Bank and the United Nations. Read the [sources and methodology](dataset/public/data#our-data-sources).

## Dataset

[OWID complete COVID-19 dataset](https://ourworldindata.org/coronavirus) provides information on **cases, deaths, testing, mortality risks, and policy responses**.

Data is updated daily, and is available back till _December 31st, 2019_.

## Accessing Data

All summary and visualizations can be found on the [OWID website](https://ourworldindata.org/coronavirus-data). The complete OWID COVID-19 dataset can be found on their [GitHub repository](https://github.com/owid/covid-19-data/tree/master/public/data#our-data-sources), or in the [`dataset/`](dataset/) directory.

## Structure

OWID COVID-19 data are stored in `/public/data` directory. 

The dataset current contains the fields:
- `iso_code`
- `continent` 
- `location` 
- `date` 
- `total_cases` 
- `new_cases` 
- `total_deaths` 
- `new_deaths` 
- `total_cases_per_million` 
- `new_cases_per_million` 
- `total_deaths_per_million` 
- `new_deaths_per_million` 
- `total_tests` 
- `new_tests` 
- `new_tests_smoothed` 
- `total_tests_per_thousand` 
- `new_tests_per_thousand` 
- `new_tests_smoothed_per_thousand` 
- `tests_per_case` 
- `positive_rate` 
- `tests_units` 
- `stringency_index` 
- `population` 
- `population_density` 
- `median_age` 
- `aged_65_older` 
- `aged_70_older` 
- `gdp_per_capita` 
- `extreme_poverty` 
- `cardiovasc_death_rate` 
- `diabetes_prevalence` 
- `female_smokers` 
- `male_smokers` 
- `handwashing_facilities` 
- `hospital_beds_per_thousand` 
- `life_expectancy`

For more information on structure and field descriptions, please see the [official documentation](https://github.com/owid/covid-19-data/blob/master/public/data/README.md).

## Attribution

> All of _Our World in Data_ is completely open access and all work is licensed under the [Creative Commons BY license](https://creativecommons.org/licenses/by/4.0/). You have the permission to use, distribute, and reproduce in any medium, provided the source and authors are credited.
