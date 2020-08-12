# New York Times COVID-19 Data

The New York Times is curating a dataset that attempts to accurately reflect the [true number of COVID-19 cases](https://www.nytimes.com/interactive/2020/us/coronavirus-us-cases.html) in the United States and around the world, despite the lack of testing in many places.

Data is compiled from state and local governments and health departments, the product of dozens of journalists working across several time zones to monitor news conferences, analyze data releases and seek clarification from public officials on how they categorize cases. For excess deaths, NYT has consulted with demographers, medical officials and local sources to confirm that this data is broadly representative of how many people have died. In some countries, the number of burials, hospital deaths or other factors are used to confirm that the underlying trends are representative.

## Datasets

The New York Times published 3 main datasets on COVID-19:

- [**Live and historical data**](#live-and-historical-data): current and historical COVID-19 cases in the US, including confirmed cases and deaths
- [**Excess deaths**](#excess-deaths): expected number of COVID-19 deaths worldwide, including those not reported in official figures
- [**Mask usage**](#mask-usage): survey of mask usage in the United States

## Accessing Data

Summary and analysis of cases data is found on the [New York Times website](https://www.nytimes.com/interactive/2020/us/coronavirus-us-cases.html).

Full dataset can be accessed from its [GitHub repository](https://github.com/nytimes/covid-19-data) or the [`dataset/`](dataset/) directory.

## Live and Historical Data

NYT is providing two sets of data with cumulative counts of coronavirus **cases** and **deaths**: one with our most current numbers for each geography and another with historical data showing the tally for each day for each geography.

Each row of data reports the cumulative number of coronavirus cases and deaths based on our best reporting up to the moment NYT publishes an update. The counts include both laboratory confirmed and probable cases using [criteria](https://int.nyt.com/data/documenthelper/6908-cste-interim-20-id-01-covid-19/85d47e89b637cd643d50/optimized/full.pdf) that were developed by states and the federal government. Not all geographies are reporting probable cases and yet others are providing confirmed and probable as a single total. Read the [methodology](https://github.com/nytimes/covid-19-data#live-and-historical-data).

Data is updated daily, and is available back till _January 21st, 2020_.

### Structure

Three files in the top-level directory of the dataset represent the historical case counts in the United States:

- [**`us.csv`**](dataset/us.csv): cumulative total cases in the US at a country level, in time-series format
- [**`us-states.csv`**](dataset/us-states.csv): cumulative total cases in each state in time-series format
- [**`us-counties.csv`**](dataset/us-counties.csv): cumulative total cases in each county, in time-series format

Live data at the country-, state-, and county-level are available in the [`live/`](live/) directory.

For information on structure and field descriptions, please read the [official documentation](https://github.com/nytimes/covid-19-data#live-and-historical-data).

## Excess Deaths

Official Covid-19 death tolls offer a limited view of the impact of the outbreak because they often exclude people who have not been tested and those who died at home. All-cause mortality is widely used by demographers and other researchers to understand the full impact of deadly events, including epidemics, wars and natural disasters. The totals in this dataset include deaths from COVID-19 as well as those from other causes, likely including people who could not be treated or did not seek treatment for other conditions. Read the [sources and methodology](https://github.com/nytimes/covid-19-data/tree/master/excess-deaths/README.md).

### Structure

Please see the [official documentation](https://github.com/nytimes/covid-19-data/tree/master/excess-deaths/README.md).

## Mask Usage

This dataset contains the number of people who answered the survey asking _"How often do you wear a mask in public when you expect to be within six feet of another person?"_. 

250,000 survey responses were received between July 2 and July 14, enough data to provide estimates more detailed than the state level.

Read the [methodology](https://github.com/nytimes/covid-19-data/tree/master/mask-use/README.md).

### Structure

Please see the [official documentation](https://github.com/nytimes/covid-19-data/tree/master/mask-use/README.md).

## Attribution

From the [official README](https://github.com/nytimes/covid-19-data/blob/master/README.md):

> In general, we are making this data publicly available for broad, noncommercial public use including by medical and public health researchers, policymakers, analysts and local news media.
> 
> If you use this data, you must attribute it to “The New York Times” in any publication. If you would like a more expanded description of the data, you could say “Data from The New York Times, based on reports from state and local health agencies.”
> 
> If you use it in an online presentation, we would appreciate it if you would link to our U.S. tracking page at [https://www.nytimes.com/interactive/2020/us/coronavirus-us-cases.html](https://www.nytimes.com/interactive/2020/us/coronavirus-us-cases.html).
> 
> If you use this data, please let us know at covid-data@nytimes.com.
> 
> See our [LICENSE](LICENSE) for the full terms of use for this data.
> 
> This license is co-extensive with the Creative Commons Attribution-NonCommercial 4.0 International license, and licensees should refer to that license ([CC BY-NC](https://creativecommons.org/licenses/by-nc/4.0/legalcode)) if they have questions about the scope of the license.

