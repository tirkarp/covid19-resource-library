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
