# Facebook Mobility Data

There are 4 sets of data in the `dataset` directory:
- Travel pattern
- Movement range
- Disease prevention map
- Inclusive Internet index

## Travel Pattern
The Travel Patterns Map shows comparisons of the number of Facebook users moving large distances (think via air or train travel) in order to provide coronavirus epidemiologists data since they no longer can rely on airline rates or baseline census/survey data for accurate counts. This is essentially looking at international travel of Facebook users. We initially are looking exclusively at international travel. The counts of travel patterns are updated daily. A minimum of 1000 unique location services users is required for us to surface the metric in order to minimize re-identification risk. 

### Problem/Use Case
Now that airline data is not usable, what are movement patterns between countries compared to pre-crisis levels?  This helps both epidemiologists and public health policy makers understand the rate at which pathogens are likely to be introduced to a population from outside. Also this data is useful for understanding the economic impact and recovery of the travel and tourism industries. 

### Schema
- `ds`: date which the data was collected defined by UTC time zone.	
- `polygon1_id`: The unique identifier of the origin location of the travel.
- `polygon1_name`: The name of the origin location (usually country name).	
- `latitude1`: The latitude of the center point of the origin polygon.	
- `longitude1`: The longitude of the center point of the origin polygon.
- `polygon2_id`: The unique identifier of the destination location of the travel. 
- `polygon2_name`: The name of the destination location (usually country name).	
- `latitude2`: The latitude of the center point of the destination polygon.
- `longitude2`: The longitude of the center point of the destination polygon.
- `metric_value`: The count of the unique number of Facebook users with Location Services enabled that traveled from the origin to the destination during the DS time period. 
- `metric_name`: Description of the metric value for visualization purposes. In this case always “travel counts”

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
