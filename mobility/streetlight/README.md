# StreetLight Data's Transportation Statistics

[StreetLight Data](https://www.streetlightdata.com/) is a company that collects transportation statistics. It focuses on analyzing patterns and forming insights using big data, and has built the industry's most comprehensive metrics that are accurate and validated.

Every month, StreetLight Data ingest, index and process over 100 billion anonymized location records from smart phones and navigation devices in connected cars and trucks. Adding context from numerous other sources like parcel data and digital road network data, they developed a view into North America’s vast network of roads, bike lanes and sidewalks. Those data are then channeled into a proprietary data processing engine to create contextualized, aggregated, and normalized travel patterns, validated with thousands of traffic counters and embedded sensors.

StreetLight Data is providing a [full suite of transportation metrics](https://www.streetlightdata.com/covid-transportation-metrics/) for the first two weeks of May and all of March and April. You will need to [contact the company](https://learn.streetlightdata.com/contact) to request access, after which they will send the `csv` files to your email. It took about a week before they got back to me.

It seems like StreetLight data is providing [statistics on the total _vehicle miles traveled (VMT)_ in a county](https://learn.streetlightdata.com/vmt-data-counties) separately. If you are in need of that data, it would be helpful to mention this to them in your conversation.

The dataset is available in the [`dataset/`](dataset/) directory.

## Datasets

Within StreetLight Data's transportation metrics, I only have access to the VMT data (13.5 MB) for the moment, available in the [`dataset` folder](dataset/). I have requested access to the full suite of transportation metrics and will put out more information once I receive them.

The VMT data contains the average and total **vehicle miles traveled** in 3,000+ U.S. counties. It fuses Cuebiq’s near-real time Mobility Index with StreetLight’s algorithms that transform location data into contextualized, aggregated, and normalized travel patterns, as well as deep repositories of data depicting historical VMT. Read the [methodology](https://www.streetlightdata.com/VMT-monitor-by-county/#methodology).

Data is updated three times a week, and is available back till _March 1st, 2020_.


## How to access data

You can explore a [map showing VMT data](https://www.streetlightdata.com/VMT-monitor-by-county/#emergency-map-response) on StreetLight Data's website.

Full VMT dataset is also publicly available in [data.world](https://data.world/associatedpress/vehicle-miles-traveled).

Please contact [StreetLight Data](https://learn.streetlightdata.com/contact) to request access. Alternatively, explore the VMT dataset in the [`dataset`](dataset/) directory. Last updated _June 4th, 2020_.


## Structure

| Field | Description | Type | Example |
|-|-|-|-|
| `statefp10`	 | Variable-digit [FIPS code] of the state in which the data is recorded | string | 1 |
| `countyfp10` | Variable-digit [FIPS code] of the county in which the data is recorded | string | 1 |
| `state_name` | Name of the state in which the data is recorded | string | Alabama |
| `county_name` | Name of the county in which the data is recorded | string | Autauga |
| `ref_dt` | Date on which the data is recorded | string | 3/1/2020 |
| `county_vmt` | Total vehicle miles traveled | integer | 3890000 |
| `jan_avg_vmt` | Average vehicle miles traveled since January 2020 | integer | 3571446 |

[FIPS code]: https://transition.fcc.gov/oet/info/maps/census/fips/fips.txt


## Attribution

No attribution information is available from StreetLight Data. Please see the [terms of use](terms-of-use.md).
