# SafeGraph Mobility Data

[SafeGraph](https://safegraph.com) is a company that curates geospatial data. It has built the most comprehensive (commercially available) database in the US for _Places (POI)_ where people spend money (~5M POI). 

Data is sourced from over 1,000 different sources which include: 1st party data, satellite imagery, business listings, store locator, municipal & government data, open source data, hand-drawn cartography etc. SafeGraph then combines them and algorithmically QA's and discards bad data. [[1](https://www.quora.com/How-does-SafeGraph-acquire-data/answer/Jason-Richman-3)]

SafeGraph is providing free access to COVID-19 datasets for researchers through the [COVID-19 Data Consortium](https://www.safegraph.com/covid-19-data-consortium). **You will need to [sign up](https://www.safegraph.com/covid-19-data-consortium) with your Purdue email** and sign the Data Use Agreement before being granted access to a Slack workspace, where you will find further instructions and resources. 

Alternatively, we have downloaded the datasets for our own use, available on [Box](https://app.box.com/s/s4wafbxi3hfv3vdwc1pj05kuiuy5p93u).




## Datasets

Among SafeGraph's various datasets, we found two that provide data related to human mobility:

- **[Weekly Patterns](#weekly-patterns)**: a dataset of visitor and demographic aggregations available for ~4.1MM POI
- **[Social Distancing Metrics](#social-distancing-metrics)**: a summary of population movement aggregated by home census block groups (CBG)

More datasets from SafeGraph can be found [here](https://docs.google.com/spreadsheets/d/1UNWvPzkUTTlXBZ6M6iGhM_7sr8h-MxsZdE7iOszkAmk/edit#gid=0).




## How to access data

Sign up for SafeGraph's [COVID-19 Data Consortium](https://www.safegraph.com/covid-19-data-consortium) with your Purdue email and join the Slack workspace. 


### Box - `csv` files (Recommended)

Access [here](https://app.box.com/s/s4wafbxi3hfv3vdwc1pj05kuiuy5p93u). Last updated _June 6th, 2020_. 


### Rill Data - SQL database, API, visualization, analytics dashboard (requires registration)

[Rill Data](https://covid.rilldata.com/) is offering a fully-managed cloud database and dashboard service, hosting a curated, continuously updated data set encompassing SafeGraph’s population movement data, Facteus’s consumer spending data, and US county level COVID-19 data from the New York Times. Read the [announcement](https://safegraphcovid19.slack.com/archives/C0115PHMGM6/p1588316365401800).

#### Tools provided:

- **[Apache Druid](https://druid.apache.org/)**: fast, in-memory cloud database
- **[Apache Superset](https://superset.incubator.apache.org/)**: create simple charts and tables
- **[Unfolded](https://www.unfolded.ai/)**: data visualization tool

#### To get started:

1. Sign up for SafeGraph's [COVID-19 Data Consortium](https://www.safegraph.com/covid-19-data-consortium) with your Purdue email and join the Slack workspace. 
2. Sign up for [Rill Data's service](https://docs.google.com/forms/d/e/1FAIpQLSf1JoBMvvdovqgH4nF-KNMVssddbxkbgx3we27tiH7B68ebIg/viewform) with your personal Gmail address.
3. (Optional) Sign up for [Unfolded Studio](https://docs.google.com/forms/d/e/1FAIpQLSdnRBTMCasEJTLjABBVV_BOUCOS-ijz5EmO0pjyOdwwjVX3tw/viewform).
4. Wait for email invitations.
5. Login [here](https://covid.rilldata.com).
6. View Apache Druid's schema [here](https://docs.google.com/spreadsheets/d/1gxBKcSjIjwBsJswA3JvjZtqBLFBssus8wO-xpUeLWYw/edit#gid=0).


### SafeGraph's AWS S3 - `csv` files

This is the official method of accessing SafeGraph datasets, hosted at `s3://sg-c19-response/`.

#### Setting up

1. Install the AWS CLI v2 according to [this instruction](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html).
2. Run `aws configure --profile safegraph`.
3. Fill in these credentials. Please keep the credentials secret for your own use.  

    ```
    Access Key: AKIAWWZ7POZOI2HE24P3
    Secret Access Key: 6NRw5H8XipyQxcTylyerWsQ0TO2VoHi1xYJL04Be
    Default region name: us-west-2
    You can leave Default output format blank
    ```
    Last updated _June 6th, 2020_. Credentials are rotated every week.

#### Downloading and using data

Different datasets will be located at different AWS S3 paths. **The location of each dataset can be found [here](https://docs.google.com/spreadsheets/d/1UNWvPzkUTTlXBZ6M6iGhM_7sr8h-MxsZdE7iOszkAmk/edit#gid=0)**.

For example, Monthly Patterns dataset is located at `s3://sg-c19-response/monthly-patterns/`.

- To view all the files, run  

    ```
    aws s3 ls s3://sg-c19-response/monthly-patterns/ --profile safegraph
    ```
    
- To download all files into your desired destination, run  

    ```
    aws s3 cp s3://sg-c19-response/monthly-patterns/ ./mylocaldirectory/ --recursive --profile safegraph
    ```

`csv` files may come compressed in `.gz` format. To unzip, run `gunzip file-name.csv.gz`.


### BigQuery - SQL database (not yet available)

Read the [announcement](https://safegraphcovid19.slack.com/archives/C0115PHMGM6/p1591205322276500). 




## [Weekly Patterns](https://docs.safegraph.com/docs/weekly-patterns)

Patterns is a dataset of visitor and demographic aggregations available for ~4.1MM POI in the United States. It contains fields such as (non-exhaustive):
- visitor count to a POI (per hour or day)
- distance from home travelled by visitors
- duration of the visits 
- other brands that visitors to a particular POI also visit


### Structure

Please see SafeGraph's documentation [here](https://docs.safegraph.com/docs/weekly-patterns).

The dataset is organized into 4 directories:
- **[main-file](https://docs.safegraph.com/docs/weekly-patterns#section-schema)**: each file contains patterns data for each week 
- **[home-summary-file](https://docs.safegraph.com/docs/weekly-patterns#section-home-location-distributions-by-state-census-block-group)**: breakdown of the home origin of the devices in each weekly patterns
- **[normalization-stats](https://docs.safegraph.com/docs/weekly-patterns#section-normalization-stats)**: information such as _total visits_ or _total devices seen_ each week for normalization
- **[release-metadata](https://docs.safegraph.com/docs/weekly-patterns#section-release-metadata)**: metadata about each week, such as _total POI_.


## Social Distancing Metrics
