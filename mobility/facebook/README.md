# Facebook Mobility Data

Facebook is providing [tools for researchers](https://dataforgood.fb.com) to use aggregated location data of opt-in Facebook users for disaster prevention purposes. Some resources they provide are publicly available (such as population density maps), while some require registration and signing the data use agreement, upon which you will be sent an invitation to a Slack workspace to access more resources.

Purdue has an existing data agreement with Facebook Data for Good, signed by [Ken Sandel](mailto:sandel@purdue.edu). Please reach out to him request access to Facebook's mobility data. 

Alternatively, we have downloaded some relevant datasets for our own use, available in the [`dataset`](dataset/) folder or on Box.



## Datasets

Among the datasets we have downloaded, we found three that provide data related to human mobility data:

- [**Travel Pattern**](#travel-pattern): # of users moving from one place to another
- [**Movement Range**](#movement-range): change in user movement compared to a baseline (publicly available)
- [**Disease Prevention Maps**](#disease-prevention-maps): a set of maps that show mass movement, population, or colocation index

More datasets can be found on [Facebook Data for Good](https://dataforgood.fb.com/docs/covid19/)'s website.

**Note**: Facebook geospatial data is built on the smallest available tile size of the [Bing Maps Tile System](https://docs.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system), and [Pittney Bowe's World Boundaries](https://dataguide.precisely.com/world-boundaries-7LP-44WA.html?utm_medium=Redirect-PB&utm_source=Direct-Traffic) for administrative regions. The fields in the datasets will be defined according to these two systems.



## How to access data

Visit [Facebook Data for Good](https://dataforgood.fb.com/docs/covid19/)'s website for publicly available datasets, and reach out to [Ken Sandel](mailto:sandel@purdue.edu) to request access to non-publicly available datasets.

Alternatively, please explore the `csv` files we have downloaded in the [`dataset`](dataset/) folder or on Box.



## Travel Pattern

The Travel Patterns Map shows comparisons of the number of Facebook users moving large distances (think via air or train travel) in order to provide coronavirus epidemiologists data since they no longer can rely on airline rates or baseline census/survey data for accurate counts. This is essentially looking at international travel of Facebook users. The counts of travel patterns are updated daily. A minimum of 1000 unique location services users is required for us to surface the metric in order to minimize re-identification risk. 

### Problem/Use Case
Now that airline data is not usable, what are movement patterns between countries compared to pre-crisis levels?  This helps both epidemiologists and public health policy makers understand the rate at which pathogens are likely to be introduced to a population from outside. Also this data is useful for understanding the economic impact and recovery of the travel and tourism industries. 

### Structure
| Field | Description | Type | Example |
|---|---|---|---|
| `ds` | Date which the data was collected defined by UTC time zone | string | 2020-02-28 |
| `polygon1_id` | Unique identifier of the origin location of the travel | string | 937148070010051 |
| `polygon1_name` | Name of the origin location (usually country name) | string | united states |
| `latitude1` | Latitude of the center point of the origin polygon | float | 40.0 |
| `longitude1` | Longitude of the center point of the origin polygon | float | -100.0 |
| `polygon2_id` | Unique identifier of the destination location of the travel | string | 381900512398634 |
| `polygon2_name` | Name of the destination location (usually country name) | string | ecuador |
| `latitude2` | Latitude of the center point of the destination polygon | float | -1.4666666666667 |
| `longitude2` | Longitude of the center point of the destination polygon | float | -78.816666666667 |
| `metric_value` | Count of the unique number of Facebook users with Location Services enabled that traveled from the origin to the destination during the `ds` time period | integer | 1995 |
| `metric_name` | Description of the metric value for visualization purposes, in this case always `travel counts` | string | travel counts |


### How was Data Gathered?
Location Services data of Facebook mobile app users (opt-in feature)

---

## Movement Range
This data includes movement changes measured by Facebook throughout March, April, and May 2020 starting from a baseline in February.

### Files
- `fips0.csv`: U.S.-wide movement
- `fips1.csv`: U.S. movement, per State
- `fips2_{state_code}.csv`: U.S. State movement, per County
- `gadm0.csv`: Movement for selected countries
- `gadm1_{iso3_code}.csv`: Movement for selected countries at regional level
- `gadm12_{iso3_code}.csv`: Movement for selected countries at sub-regional level

### Schema
- `state_fips`: Two-digit FIPS code representing a U.S. State, e.g. 06 for California
- `county_fips`: Five-digit FIPS code representing a U.S. County, e.g. 06001 for Alameda, CA
- `gadm_code`: Alphanumeric country, region, or sub-region code referencing GADM.org data
- `metric_date`: date which the data was collected
- `all_day_bing_tiles_visited_relative_change`: Positive or negative change in movement relative to baseline
- `all_day_ratio_single_tile_users`: Positive proportion of users staying put within a single location

---

## Disease Prevention Map
This data is divided into multiple categories:
- Movement maps (between tiles and administrative region)
- Population maps (tile level and admin region level)
- Colocation map

### Movement Maps
Movement Maps illustrate aggregate patterns of movement of Facebook users with location history turned on over a period of several hours. There are two map options for showing movement. The maps are prepared at two different levels of aggregation. The "movement between tiles" maps show patterns of movement between individual bing tiles. Meanwhile, the "movement between administrative regions" maps show patterns of movement between neighborhoods, cities, or districts.

The following metrics are represented by the movement maps:

- Baseline: the average number of people who moved between these two locations before the maps were generated, typically from 7-40 days preceding the first day for which the maps were kicked off.
- Crisis: the number of people today that moved from that tile to another tile with location history turned on.

### Population Maps
Facebook Population Maps show the density of people using Facebook on their mobile phones with location history turned on. Tile level maps show the approximate number of people with location history enabled in a tile, whereas administrative maps show the approximate number of people with location history enabled in an administrative boundary.

The following metrics are represented by the population maps:

- Baseline: the average number of people in this location before the maps were generated, typically from 7-40 days preceding the first day for which the maps were kicked off.
- Crisis: the number of people that appear today in that tile.

### Colocation Map
Colocation maps are spatial network datasets, provided as part of Disease Prevention Maps, that estimate how often people from different regions are colocated. In particular, these maps estimate, for each pair of regions x and y, the probability of a randomly chosen person from x and from y being colocated in the same place during a randomly chosen minute for a given week. Same place implies within the same level 16 Bing tile, which roughly corresponds to a 0.6 km by 0.6 km square, depending on the latitude.

As a concrete example: if you choose a random person from Los Angeles County and a random person from San Francisco County, what is the probability that in a random minute they are in the same level 16 Bing tile anywhere in the world during a week? Colocation Maps answer this question. By multiplying by the number of minutes in a week, Colocation Maps provide an estimate of the expected total number of minutes two random people from two regions spend colocated.

The following metrics are represented by the colocation maps:

- Colocation probability: for a pair of regions indicates the probability that two random users assigned to those regions are colocated on a random minute during the week.

---

### Inclusive Internet Index

The Inclusive Internet Index, commissioned by Facebook and conducted by The Economist Intelligence Unit, seeks to measure the extent to which the Internet is not only accessible and affordable, but also relevant to all, allowing usage that enables positive social and economic outcomes at the individual and group level.
