# Facebook Mobility Data

Facebook is providing [tools for researchers](https://dataforgood.fb.com) to use aggregated location data of opt-in Facebook users for disaster prevention purposes. Some resources they provide are publicly available (such as population density maps), while some require registering and signing the data use agreement, upon which you will be sent an invitation to a Slack workspace and the [GeoInsights Portal][1].

Purdue has an existing data agreement with Facebook Data for Good, signed by [Ken Sandel](mailto:sandel@purdue.edu). Please reach out to him to request access to Facebook's mobility data. 

Alternatively, we have downloaded some relevant datasets for our own use, available in the [`dataset`](dataset) directory or on Box.



## Datasets

Among the datasets we have downloaded, we found three that provide data related to human mobility:

- [**Travel Pattern**](#travel-pattern): # of users moving from one place to another
- [**Movement Range**](#movement-range): change in user movement compared to a baseline (publicly available)
- [**Disease Prevention Maps**](#disease-prevention-maps): a set of maps that show mass movement, population, or colocation index

More datasets can be found on [Facebook Data for Good](https://dataforgood.fb.com/docs/covid19)'s website.

**Note**: Facebook geospatial data is built on the smallest available tile size of the [Bing Maps Tile System](https://docs.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system#ground-resolution-and-map-scale), and [Pittney Bowe's World Boundaries](https://dataguide.precisely.com/world-boundaries-7LP-44WA.html?utm_medium=Redirect-PB&utm_source=Direct-Traffic) for administrative regions. The fields in the datasets will be defined according to these two systems.



## How to access data

Visit [Facebook Data for Good](https://dataforgood.fb.com/docs/covid19)'s website for publicly available datasets, and reach out to [Ken Sandel](mailto:sandel@purdue.edu) to request access to non-publicly available datasets.

Alternatively, please explore the `csv` files we have downloaded in the [`dataset`](dataset/) folder or on Box. (~103 MB)

-----

## Travel Pattern

The Travel Patterns Map shows comparisons of the number of Facebook users moving large distances (think air or train travel). This is essentially looking at international travel of Facebook users. This data comes in useful because airline data is no longer accurate amidst the disruptions. 

Data is released daily, and is available back till _February 28th, 2020_.

### Structure

| Field | Description | Type | Example |
|-|-|-|-|
| `ds` | Date which the data was collected, in the form `YYYY-MM-DD` | string | 2020-02-28 |
| `polygon1_id` | Unique identifier of the [origin location][2] of the travel | string | 937148070010051 |
| `polygon1_name` | Name of the [origin location][2] (usually country name in lowercase) | string | united states |
| `latitude1` | Latitude of the center point of the origin polygon | float | 40.0 |
| `longitude1` | Longitude of the center point of the origin polygon | float | -100.0 |
| `polygon2_id` | Unique identifier of the [destination location][2] of the travel | string | 381900512398634 |
| `polygon2_name` | Name of the [destination location][2] (usually country name in lowercase) | string | ecuador |
| `latitude2` | Latitude of the center point of the destination polygon | float | -1.4666666666667 |
| `longitude2` | Longitude of the center point of the destination polygon | float | -78.816666666667 |
| `metric_value` | Count of the unique number of Facebook users with location services enabled, that traveled from the origin to the destination during the `ds` time period | integer | 1995 |
| `metric_name` | Description of the metric value for visualization purposes, in this case always `travel counts` | string | travel counts |



## Movement Range

_**Update**: Facebook has released a new version of the Movement Range Maps. Information below will be updated to match the new version soon._

Movement Range Maps is a dataset that answers how populations are responding to physical distancing measures. It includes movement changes throughout March, April, and May 2020 starting from a baseline in February. 

This dataset shows two different metrics: 

- **Change in Movement**: looks at how much people are moving around and compares it to a baseline period that predates most social distancing measures
- **Stay Put**: looks at the fraction of the population that appears to stay within a small area surrounding their home for an entire day

This dataset is publicly available on [Facebook Data for Good website](https://dataforgood.fb.com/docs/covid19). Data is released daily, and is available back till _March 1st, 2020_.

### Structure

Files in this dataset is organized under the naming system described below.

- `fips0.csv`: U.S.-wide movement
- `fips1.csv`: U.S. movement, per State
- `fips2_{state-code}.csv`: U.S. State movement, per County
- `gadm0.csv`: Movement for selected countries
- `gadm1_{iso3-code}.csv`: Movement for selected countries at regional level
- `gadm12_{iso3-code}.csv`: Movement for selected countries at sub-regional level

Each file may contain some of the following fields:

| Field | Description | Type | Example |
|-|-|-|-|
| `level` | Granularity of data: <ul><li>`0` for country-level</li><li>`1` for 1st administrative level</li><li>`2` for 2nd administrative level</li></ul> | integer | 0 |
| `polygon_id` | Unique identifier of the [administrative unit][2]  | string | 1001 |
| `polygon_name` | Name of the [administrative unit][2] | string | Autauga |
| `state_fips` | Two-digit [FIPS code] representing a U.S. State, e.g. `06` for California | string | 01 |
| `county_fips` | Five-digit [FIPS code] representing a U.S. County, e.g. `06001` for Alameda, CA | string | 01001 |
| `gadm_code` | Alphanumeric country, region, or sub-region code referencing gadm.org data | string | AUS |
| `metric_date` | Date which the data was collected, in the format `YYYY-MM-DD` | string | 2020-03-01 |
| `all_day_bing_tiles_visited_relative_change` | Positive or negative change in movement relative to baseline | float | 0.04629090414434283 |
| `all_day_ratio_single_tile_users` | Positive proportion of users staying put within a single location | float | 0.18034684254668779 |


[FIPS code]: https://transition.fcc.gov/oet/info/maps/census/fips/fips.txt

---

## Disease Prevention Maps

Disease Prevention Maps is a dataset designed to help organizations close gaps in understanding where people live, how people are moving, and the state of their cellular connectivity, in order to improve the effectiveness of health campaigns and epidemic response. 

This dataset is only crisis-specific and region-specific. e.g. it only provides information for the _US Midwest_, or the _US Eastern time zone_ region for COVID-19 purposes starting and ending on specific dates (such as _May 29 - June 23_). How Facebook determines these categorization seems arbitrary to me at the moment. As far as I am concerned, however, individual researchers can request for a specific data on `#data_requests` in Slack.

Within each region, a few maps are provided:

- [Movement Maps](#movement-maps) (between tiles and administrative region)
- [Population Maps](#population-maps) (tile level and administrative region level)
- [Colocation Maps](#colocation-maps)

Some regions provide more types of maps than listed here. In addition, there is an interactive map that you can launch on [GeoInsights Portal][1] that shows the dataset in action.

Each map (at a specific data at a specific time) will be its own `.csv` file. You can search for all available Disease Prevention Maps on the [GeoInsights Portal][1]. Data for coronavirus maps are usually updated three times a day at 0000hr, 0800hr and 1600hr.


### Movement Maps

Movement Maps illustrate aggregate patterns of movement of Facebook users with location history turned on over a period of several hours. There are two map options for showing movement. The maps are prepared at two different levels of aggregation. The _Movement between tiles_ maps show patterns of movement between individual Bing tiles. Meanwhile, the _Movement between administrative regions_ maps show patterns of movement between neighborhoods, cities, or districts.

The following [metrics](https://www.facebook.com/help/geoinsights/591245441383373/?helpref=hc_fnav&bc[0]=SPACO%20Help%20Center&bc[1]=Disease%20Prevention%20Maps) are represented by the movement maps:

- **Baseline**: the average number of people who moved between two locations before the maps were generated, typically from 7-40 days preceding the first day for which the maps were kicked off. Read more in this [Slack thread][3].
- **Crisis**: the number of people on a given day that moved from a location to another location with location history turned on

Some regions also provide an _Interactive Movement Map_, which is almost exactly the same as the _Movement between administrative regions_ map, but optimized for use in interactive maps.

#### Structure

Each movement map may contain some of the following fields:

| Field | Description | Type | Example |
|-|-|-|-|
| `geometry` | Type of geometrical object represented, typically a [`LINESTRING`](https://docs.microsoft.com/en-us/sql/relational-databases/spatial/linestring?view=sql-server-ver15) | LINESTRING array | `LINESTRING (-73.98193359374999 40.363286261845936, -73.98193359374999 40.363286261845936)` |
| `date_time` | Date and time at which the data was collected in UTC, in the format `YYYY-MM-DD HHMM` (24-hour format) | string | 2020-04-28 1600 |
| `start_polygon_id` | Unique identifier of the [starting location][2] | string | 1206879 |
| `start_polygon_name` | Name of the [starting location][2] | string | Rumson |
| `end_polygon_id` | Unique identifier of the [ending lcation][2] | string | 1206879 |
| `end_polygon_name` | Name of the [ending location][2] | string | Rumson |
| `length_km` | Total distance of movement in kilometers | float | 0 |
| `tile_size` | Level of the region represented by the [Bing Maps Tile System](https://docs.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system#ground-resolution-and-map-scale) | integer | 13 |
| `country` | Name of the country in which the data is collected | string | US |
| `level` | Level of administrative region represented, usually in the form `LEVEL#`, where `#` is the level number | string | LEVEL4 |
| `n_crisis` | Total number of people who moved from starting location to ending location. [Read more][4] | float | 189 |
| `n_baseline` | Average total number of people who moved from starting location to ending location on average during the weeks before the crisis began. [Read more][4]. | float | 125.8 |
| `n_difference` | `n_crisis` - `n_baseline`, i.e. difference between the number of people moving from starting location to ending location during the crisis compared to before the crisis | float | 63.2 |
| `percent_change` | `n_difference` divided by `n_baseline`, in percentage. i.e. percentage difference between the number of people moving from starting location to ending location during the crisis compared to before the crisis | float | 49.842271293375 |
| `is_statistically_significant` | Number indicating if the metric is statistically significant. `0` if no and `1` if yes (needs verification). | integer | 0 |
| `z_score` | Number of standard deviations by which the count of people moving during the crisis differs from the number of people moving during the baseline. Any z-value greater than `4` or smaller than `-4` is clipped at `4` or `-4`. | float | 4 |
| `start_lat` | Latitude of the starting location | string | 40.362226449936 |
| `start_lon` | Longitude of the starting location | string | -74.00448748566 |
| `end_lat` | Latitude of the ending location | string | 40.362226449936 |
| `end_lon` | Longitude of the ending location | string | -74.00448748566 |
| `start_quadkey` | Unique identification of the starting tile at a particular level of detail (_quad key_ according to the [Bing Maps Tile System](https://docs.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system#tile-coordinates-and-quadkeys)) | string | 320101121120 |
| `end_quadkey` | Unique identification of the ending tile at a particular level of detail (_quad key_ according to the [Bing Maps Tile System](https://docs.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system#tile-coordinates-and-quadkeys)) | string | 320101121120 |

**Note**: any missing value is represented with a `\N`.


### Population Maps

Facebook Popoulation Maps are heat maps, which show where people are located before, during and after a disaster and where populations have increased or decreased.
They highlight the density of people using Facebook on their mobile phones with location history turned on. Like the Movement Maps, Population Maps are available at two different levels of aggregation: _Tile level_ maps show the approximate number of people with location history enabled in a Bing tile, whereas _Administrative region_ maps show the approximate number of people with location history enabled in an administrative boundary.

The following [metrics](https://www.facebook.com/help/geoinsights/591245441383373/?helpref=hc_fnav&bc[0]=SPACO%20Help%20Center&bc[1]=Disease%20Prevention%20Maps) are represented by the population maps:

- **Baseline**: the average number of people in this location before the maps were generated, typically from 7-40 days preceding the first day for which the maps were kicked off. Read more in this [Slack thread][3].
- **Crisis**: the number of people that appear on a given day at a given location

#### Structure

Each population map may contain some of the following fields:

| Field | Description | Type | Example |
|-|-|-|-|
| `spaco_id` | Unique identification for a boundary in [Pittney Bowe's World Boundaries](https://dataguide.precisely.com/world-boundaries-7LP-44WA.html?utm_medium=Redirect-PB&utm_source=Direct-Traffic) | string | 50857 |
| `lat` | Latitude of the location | string | 39.064025405394 |
| `lon` | Longitude of the location | string | -75.599111953732 |
| `quadkey` | Unique identification of a tile at a particular level of detail (_quad key_ according to the [Bing Maps Tile System](https://docs.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system#tile-coordinates-and-quadkeys)) | string | 3201010333103 |
| `country` | Name of the country in which the data is collected | string | US |
| `polygon_name` | Name of the location in which data is collected | string | Central Kent |
| `level` | Level of administrative region represented, usually in the form `LEVEL#`, where `#` is the level number | string | LEVEL4 |
| `date_time` | Date and time at which the data was collected in UTC, in the format `YYYY-MM-DD HHMM` (24-hour format) | string | 2020-04-28 1600 |
| `n_baseline` | Average total number of people that was expect to be in the area based on pre-disaster estimates. [Read more][4]. | float | 1863.5277871879 |
| `n_crisis` | Total number of people observed at a given location. [Read more][4] | integer | 2252 |
| `n_difference` | `n_crisis` - `n_baseline`, i.e. difference between the population at the time of the crisis and the population during the baseline | float | 28.6263067187692 |
| `density_baseline` | Ratio of users in the given area over the sum of all users in the entire dataset (i.e. all other tiles in the boundary box) based on pre-disaster estimates | float | 0.0000386134397106904 |
| `density_crisis` | Ratio of users in the given area over the sum of all users in the entire dataset (i.e. all other tiles in the boundary box) during the crisis | float | 0.0000241786401705555 |
| `percent_change` | `n_difference` divided by `n_baseline`, in percentage. i.e. percentage difference between the population at the time of the crisis and the population during the baseline | float | -37.0096374211798 |
| `clipped_z_score` | Number of standard deviations by which the crisis population count in the location differs from the baseline count. Any z-value greater than `4` or smaller than `-4` is clipped at `4` or `-4`. | float | 3.9523934544576 |
| `ds` | Date in the form `M/D/YYYY`. What it represents is unknown and should be asked on Slack. | string | 6/3/2020 |

**Note**: any missing value is represented with a `\N`.


### Colocation Maps
Colocation maps are spatial network datasets, provided as part of Disease Prevention Maps, that estimate how often people from different regions are colocated. In particular, these maps estimate, for each pair of regions x and y, the probability of a randomly chosen person from x and from y being colocated in the same place during a randomly chosen minute for a given week. Same place implies within the same level 16 Bing tile, which roughly corresponds to a 0.6 km by 0.6 km square, depending on the latitude.

As a concrete example: if you choose a random person from Los Angeles County and a random person from San Francisco County, what is the probability that in a random minute they are in the same level 16 Bing tile anywhere in the world during a week? Colocation Maps answer this question. By multiplying by the number of minutes in a week, Colocation Maps provide an estimate of the expected total number of minutes two random people from two regions spend colocated.

The following metrics are represented by the colocation maps:

- Colocation probability: for a pair of regions indicates the probability that two random users assigned to those regions are colocated on a random minute during the week.


---


#### Notes about `n_baseline` and `n_crisis`

Facebook described the methodology for calculating `n_baseline` as follows:

> The baseline period differs slightly by map type: Facebook Population is 90 days, Movement Maps are 45 days. This is the number of days going back from the day the maps were kicked off (you can see this by looking at the day the first data is generated). 
> 
> The baseline value is segmented by the day of the week and the time window for the metric. Thus the baseline value for _00:00 UTC_ on a Tuesday is the mean value (outliers are winsorized, not removed) across all the _00:00 UTC_ + Tuesdays in the 45 days prior to when the maps first generated. This means the baseline is a set period of days prior to day zero on the maps - it is **NOT** a rolling window. 
> 
> So for example the Movement between Tiles data set will have 7 days * 3 eight hour time windows (00:00 UTC, 08:00 UTC, and 16:00 UTC) = 21 unique baseline values across the data set.

They also described what `n_crisis` actually represents:

> `n_crisis` is not exactly number of users who traveled. It is all the users who had the start location as their most common location during the first 8 hour time window and end location as their most common location in the second 8 hour time window (the start of the second window is the one that gives the row it's value on the time series). 
> 
> This means that start and end location can be the same for users who did not leave, or also for those users who left but for not long enough to change the most common location during either 8 hour window.

Read more in the [Slack thread][3].


[1]: https://www.facebook.com/geoinsights-portal
[2]: https://docs.microsoft.com/en-us/bingmaps/v8-web-control/map-control-api/polygon-class
[3]: https://fbdataforgood.slack.com/archives/CBHC1BHAS/p1592319586456400
[4]: #notes-about-n_baseline-and-n_crisis



### Inclusive Internet Index

The Inclusive Internet Index, commissioned by Facebook and conducted by The Economist Intelligence Unit, seeks to measure the extent to which the Internet is not only accessible and affordable, but also relevant to all, allowing usage that enables positive social and economic outcomes at the individual and group level.
