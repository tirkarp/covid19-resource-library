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

## Movement Range
This data includes movement changes measured by Facebook throughout March, April, and May 2020 starting from a baseline in February.

### Files
- `fips0.csv`: U.S.-wide movement
- `fips1.csv`: U.S. movement, per State
- `fips2\_{state\_code}.csv`: U.S. State movement, per County
- `gadm0.csv`: Movement for selected countries
- `gadm1\_{iso3\_code}.csv`: Movement for selected countries at regional level
- `gadm12\_{iso3\_code}.csv`: Movement for selected countries at sub-regional level

### Schema
- `state_fips`: Two-digit FIPS code representing a U.S. State, e.g. 06 for California
- `county_fips`: Five-digit FIPS code representing a U.S. County, e.g. 06001 for Alameda, CA
- `gadm_code`: Alphanumeric country, region, or sub-region code referencing GADM.org data
- `all_day_bing_tiles_visited_relative_change`: Positive or negative change in movement relative to baseline
- `all_day_ratio_single_tile_users`: Positive proportion of users staying put within a single location

