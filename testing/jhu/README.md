# John Hopkins University COVID-19 Dataset

John Hopkins University Center for Systems Science and Engineering (CSSE) aggregates and analyzes [the best data available on COVID-19](https://coronavirus.jhu.edu/) worldwide — including cases, as well as testing, contact tracing and vaccine efforts — to help the public, policymakers and healthcare professionals respond to the pandemic.

Data is collected from multiple offical and unofficial sources to provide cases information up to the city/county level. JHU CSSE then cleans and combines the data into one massive dataset.

## Dataset

JHU CSSE COVID-19 Dataset contains a daily summary of **active, confirmed, recovered cases, and the fatality of cases** in each location.

Data is updated daily, and is available back till _January 22nd, 2020_.

## Accessing Data

You can view maps, visualizations, and daily summary of JHU CSSE COVID-19 dataset on its website at coronavirus.jhu.edu, or visit the [GitHub repository](https://github.com/CSSEGISandData/COVID-19) for access to dataset files. 

Alternatively, you can access the dataset via the [`dataset/`](dataset/) directory.

## Structure

The dataset is divided into three directories:

- [**`csse_covid_19_data/`**](dataset/csse_covid_19_data): daily reports and timeseries data of cases around the world
- [**`who_covid_19_situation_reports/`**](dataset/who_covid_19_situation_reports): [WHO COVID-19 Situation Reports](https://www.who.int/emergencies/diseases/novel-coronavirus-2019/situation-reports/) to compare discrepancy and complement CSSE case data. Read the [rationale](dataset/who_covid_19_situation_reports/README.md).
- [**`archived_data`**](dataset/archived_data): archived data in the deprecated format, containing cases from 01/21/2020 to 02/14/2020

To see field descriptions for the CSSE dataset, read the [dataset readme](dataset/csse_covid_19_data/README.md)

## Attribution

> 1. This data set is licensed under the Creative Commons Attribution 4.0 International (CC BY 4.0) by the Johns Hopkins University on behalf of its Center for Systems Science in Engineering.  Copyright Johns Hopkins University 2020. 
> 
> 2. Attribute the data as the "COVID-19 Data Repository by the Center for Systems Science and Engineering (CSSE) at Johns Hopkins University" or "JHU CSSE COVID-19 Data" for short, and the url: https://github.com/CSSEGISandData/COVID-19.  
> 
> 3. For publications that use the data, please cite the following publication: "Dong E, Du H, Gardner L. An interactive web-based dashboard to track COVID-19 in real time. Lancet Inf Dis. 20(5):533-534. doi: 10.1016/S1473-3099(20)30120-1"
