# SafeGraph Mobility Data

[SafeGraph](https://safegraph.com) is a company that curates geospatial data. It has built the most comprehensive (commercially available) database in the US for _Places (POI)_ where people spend money (~5M POI). 

Data is sourced from over 1,000 different sources which include: 1st party data, satellite imagery, business listings, store locator, municipal & government data, open source data, hand-drawn cartography etc. SafeGraph then combines them and algorithmically QA's and discards bad data. [[1](https://www.quora.com/How-does-SafeGraph-acquire-data/answer/Jason-Richman-3)]

SafeGraph is providing free access to COVID-19 datasets for researchers through the [COVID-19 Data Consortium](https://www.safegraph.com/covid-19-data-consortium). You will need to sign up with your Purdue email and sign the Data Use Agreement before being granted access to a Slack group, where you will find further instructions and resources. Alternatively, we have downloaded the datasets for our own use, available on [Box](https://app.box.com/s/s4wafbxi3hfv3vdwc1pj05kuiuy5p93u).

## Datasets

Among SafeGraph's various datasets, we found three that provide data related to human mobility:

- **[Weekly Patterns](#weekly-patterns)**: a dataset of visitor and demographic aggregations available for ~4.1MM POI
- **[Social Distancing Metrics](#social-distancing-metrics)**: a summary of population movement aggregated by home census block groups (CBG)

More datasets from SafeGraph can be found [here](https://docs.google.com/spreadsheets/d/1UNWvPzkUTTlXBZ6M6iGhM_7sr8h-MxsZdE7iOszkAmk/edit#gid=0).


## How to access data

### Box (Recommended)
Access [here](https://app.box.com/s/s4wafbxi3hfv3vdwc1pj05kuiuy5p93u). Last updated _June 6th, 2020_.

### SafeGraph's AWS S3

This is the official method of accessing SafeGraph datasets, hosted at `s3://sg-c19-response/`.

#### Setting up
1. Install the AWS CLI v2 according to [this instruction](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
2. Run `aws configure --profile safegraph`
3. Fill in these credentials. Please keep the credentials secret for our own use.  
```
Access Key: AKIAWWZ7POZOI2HE24P3
Secret Access Key: 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
Default region name: us-west-2
You can leave Default output format blank
```
Last updated _June 6th, 2020_. Credentials are rotated every week.

#### Downloading data
Different datasets will be located at different AWS S3 paths. **The location of each dataset can be found [here](https://docs.google.com/spreadsheets/d/1UNWvPzkUTTlXBZ6M6iGhM_7sr8h-MxsZdE7iOszkAmk/edit#gid=0)**.

For example, Monthly Patterns dataset is located at `s3://sg-c19-response/monthly-patterns/`.

- To view all the files, run  
```
aws s3 ls s3://sg-c19-response/monthly-patterns/ --profile safegraph
```
- To copy ALL files into your desired destination, run  
```
aws s3 cp s3://sg-c19-response/monthly-patterns/ ./mylocaldirectory/ --recursive --profile safegraph
```

### RillData (dashboard)

### BigQuery (planned development)



## Weekly Patterns

Patterns is a dataset of visitor and demographic aggregations available for ~4MM POI.

### Structure
| Column Name | Description | Type | Example |
|---|---|---|---|
| safegraph_place_id | Unique and consistent ID that is tied to this POI. | String | sg:64d0ee4695af4ab4906fe82997ead9ff |
| location_name | The name of the place of interest. | String | Salinas Valley Ford Lincoln |
| street_address | Street address of the place of interest. | String | 1100 Auto Center Circle |
| city | The city in which this point of interest is located. | String | Irvine |
| region | The state or territory. | String | CA |
| postal_code | 5 digit zip code | String | 92602 |
| iso_country_code | The 2 letter ISO 3166-1 alpha-2 country code. | String | US |
| safegraph_brand_ids | Unique and consistent ID that represents this specific brand. | List | SG_BRAND_80ca06abfa1a5104af9a770f485dad07, SG_BRAND_aa45997477591e27601c436bcb228d6f  |
| brands | If this POI is an instance of a larger brand that we have explicitly identified, this column will contain that brand name. This is an easy way to, for example, unambiguously select all Target stores in the USA. A POI may have multiple brands, as in a new car dealership that sells ford and lincoln cars. | List | ford, lincoln |
| date_range_start | Start time for measurement period in ISO 8601 format of YYYY-MM-DDTHH:mm:SS±hh:mm (local time with offset from GMT).  The start time will be 12 a.m. Monday in local time. | String | 2020-03-02T00:00:00-06:00 |
| date_range_end | End time for measurement period in ISO 8601 format of YYYY-MM-DDTHH:mm:SS±hh:mm (local time with offset from GMT).  The end time will be the following Monday at 12 a.m. local time. | String | 2020-03-09T00:00:00-06:00 |
| raw_visit_counts | Number of visits in our panel to this POI during the date range. | Integer | 1542 |
| raw_visitor_counts | Number of unique visitors from our panel to this POI during the date range. | Integer | 1221 |
| visits_by_day | The number of visits to the POI each day (local time) over the covered time period. | JSON [Integer] | [33, 22, 33, 22, 33, 22, 22] |
| visits_by_each_hour | The number of visits to the POI for each of the 168 hours of the week. | JSON [Integer] | [33, 22, 33, 22, 33, 22, 22, 21, 23, 33, 22, 11, 44, 22, 22, 44, 11, 33, 44, 44, 44, 33, 34, 44, 22, 33, 44, 44, 34, 43, 43...] |
| poi_cbg | The census block group the POI is located within. | String | 560610112022 |
| visitor_home_cbgs | A mapping of census block groups to the number of visitors to the POI whose home is in that census block group. See Privacy Section below. | JSON {String: Integer} | {"360610112021": 603, "460610112021": 243, "560610112021": 106, "660610112021": 87, "660610112021": 51} |
| visitor_daytime_cbgs | A mapping of census block groups to the number of visitors to the POI whose primary daytime location between 9 am - 5 pm is in that census block group. Only cbgs with at least 2 devices are shown and cbgs with less than 5 devices are reported as 4. See more on privacy here: Places Manual. | JSON {String: Integer} | {"360610112030": 9872, "880610112021": 8441, "569610112020": 5671, "160610112041": 2296, "980610112021": 1985} |
| visitor_country_of_origin | A mapping of country code to the number of visitors to the POI whose home is in that country. See Privacy Section below. | JSON {String: Integer} | {"US": 98,"CA": 12} |
| distance_from_home | Median distance from home traveled by visitors (of visitors whose home we have identified) in meters. If we have fewer than 5 visitors to a POI, the value will be null. | Integer | 1211 |
| median_dwell | Median minimum dwell time in minutes. | Double | 5 |
| bucketed_dwell_times | Key is range of minutes and value is number of visits that were within that duration. | JSON {String: Integer} | { "<5": 40, "5-20": 22, "21-60": 45, "61-240": 3,">240": 5} |
| related_same_day_brand | Other brands that the visitors to this POI visited on the same day as the visit to this POI where customer overlap differs by at least 5% from the SafeGraph national average. The mapping has the brand as the key. The value shown for each brand is a percentage representing the median of the following calculation for each day in the month: (same-day visitors to both the brand and the POI / total daily visitors to the POI) - (daily visitors to the brand / all visitors in SafeGraph panel).  This column will only contain values if there are at least 5 visitors to the POI. | JSON {String: Integer} | {"mcdonalds": 7,"amc": 5,"target": 3} |
| related_same_week_brand | Other brands that the visitors to this POI visited in the same week as the visit to this POI where customer overlap differs by at least 5% from the SafeGraph national average. The value shown for each brand is a percentage representing: (visitors to both the brand and the POI / total visitors to the POI) - (visitors to the brand / all visitors in SafeGraph panel). This column will only contain values if there are at least 5 visitors to the POI. | JSON {String: Integer} | {"mcdonalds": 7,"amc": 5,"target": 3} |
| device_type | The number of visitors to the POI that are using android vs. ios. See Privacy Section below. | JSON {String: Integer} | {"android": 6, "ios": 8} |
| Column Name | Description | Type | Example |
| date_range_start | Start time for measurement period in ISO 8601 format of YYYY-MM-DDTHH:mm:SS±hh:mm (local time with offset from GMT).  The start time will be 12 a.m. Sunday in local time. | String | 2020-03-01T00:00:00-06:00 |
| date_range_end | End time for measurement period in ISO 8601 format of YYYY-MM-DDTHH:mm:SS±hh:mm (local time with offset from GMT).  The end time will be the following Sunday at 12 a.m. local time. | String | 2020-03-08T00:00:00-06:00 |
| state | Lowercase abbreviation of U.S. state or territory | String | ca |
| census_block_group | FIPS code for this Census block group | String | 530330080012 |
| number_devices_residing | Number of distinct devices observed with a primary nighttime location in the specified census block group. | Integer | 54481 |


## Social Distancing Metrics
