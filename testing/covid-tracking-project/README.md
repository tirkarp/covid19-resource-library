# The COVID Tracking Project Racial Tracker

[The COVID Tracking Project](https://covidtracking.com/) is a volunteer organization launched from The Atlantic dedicated to collecting and publishing the data required to understand the COVID-19 outbreak in the United States.

Every day, the Tracking Project volunteers collect official data on COVID-19 testing and patient outcomes from all 50 states, 5 territories, and the District of Columbia. The dataset is currently in use by national and local news organizations across the United States, and by research projects and agencies worldwide. Its data API receives about two million requests per day. Read the [methodology](https://covidtracking.com/about-data/sources).

## Dataset 

The COVID Tracking Project offers a dataset containing the daily historical case counts of **positive cases**, **negative cases**, **recovered cases**, **deaths**, **testing rates**, **hospital utilization** by state, region, and country-wide total.

Apart from the cases dataset, the Tracking Project also features the [racial and ethnicity dataset](https://covidtracking.com/race) associated with COVID-19, and the [long-term medical care infrastructure](https://covidtracking.com/data/longtermcare) available.

Data is updated every day, and is available back till _January 22th, 2020_.

## Accessing Data

You can view the data dashboard on [The COVID Tracking Project website](https://covidtracking.com/) for summary, charts, and analysis.

Live data entry is available on [Google Sheets](https://docs.google.com/spreadsheets/u/2/d/e/2PACX-1vRwAqp96T9sYYq2-i7Tj0pvTf6XVHjDSMIKBdZHXiCGGdNC0ypEU9NbngS8mxea55JuCFuua1MUeOj5/pubhtml#). It can also be obtained through an API. See the [API documentation](https://covidtracking.com/data/api).

Alternatively, download the `.csv` file from the [website](https://covidtracking.com/data/download) or find it in the [`dataset/`](dataset/) directory. 

Last updated _August 12th, 2020_.

## Structure

The COVID Tracking Project total cases data are divided into two files:

- [**`daily.csv`**](dataset/daily.csv): daily US total cases in timeseries format
- [**`daily-state.csv`**](dataset/daily-state.csv): daily total cases in each state in timeseries format

## Field Description

Please read the official [data dictionary](https://covidtracking.com/about-data/data-definitions).

**Note**: Fields may be empty.

## Attribution

The COVID Tracking Project data is published under a [Creative Commons CC BY-NC-4.0](http://creativecommons.org/licenses/by-nc/4.0/) license, which requires users to attribute the source and license type (CC BY-NC-4.0) when sharing our data or website content.
