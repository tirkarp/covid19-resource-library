# Descartes Lab's Data for Mobility Changes in Response to COVID-19

[Descartes Labs](https://descarteslabs.com/) is a company that provides clean, analysis-ready geospatial data from leading public and private sources. It has built a collaborative platform that work with petabytes of that data, that can be used to gain insights and answer some of the most complex and pressing geospatial analytics questions.

Data is sourced from satellite imagery and proprietary third-party vendors. Multiple datasets that provide multiband optical, hi-res optical, atmospheric, meteorological, hydrological, land use, etc., data are avaialble.

Descartes Labs is [releasing mobility statistics](https://www.descarteslabs.com/mobility/) (representing the distance a typical member of a given
population moves in a day) at the state and county level. It is publicly available on [Descartes Labs' GitHub repo](https://github.com/descarteslabs/DL-COVID-19).

Alternatively, you can access Descartes Labs' data through our `dataset` directory.


## Datasets

[Descartes Labs' dataset](https://github.com/descarteslabs/DL-COVID-19) features the distance a typical member of a given population moves in a day, along with the number of samples collected and the percentage of the normal distance in a region.

This dataset is aggregated through four types of sources: 
- **Aggregated mobility tracking** through location tracking, changes in social activity
- **Location-specific activity tracking** that tracks activities at a micro scale
- **Regional NO2 tracking** produced by vehicles and power plants, which can be used to represent human movement
- **Supply chain tracking** radio signal from ships that can be used to track economic movement

Read the [blog post](https://medium.com/descarteslabs-team/covid-19-the-road-to-economic-and-social-recovery-6638866e3e4c) to understand more about the dataset, or read [the paper](https://arxiv.org/pdf/2003.14228.pdf) that describes the motivation behind the methodology.

Data is updated daily, and is available back till _March 1st, 2020_.


## How to access data

You can view a visualization of the changes in US mobility on [Descartes Labs' website](https://www.descarteslabs.com/mobility/). Or, download the dataset through Descartes Labs' [GitHub repo](https://github.com/descarteslabs/DL-COVID-19), or throuh our `dataset` directory.

A [script](https://github.com/descarteslabs/DL-COVID-19/tree/master/scripts) is available to plot mobility index.


## Structure

Please read Descartes Labs' [documentation](https://github.com/descarteslabs/DL-COVID-19/blob/master/README.md).

This dataset is available in `csv` and [`ndjson`](https://github.com/ndjson/ndjson-spec) formats. It is organized as 5 different files:

- [**`DL-us-mobility.ndjson`**](https://github.com/descarteslabs/DL-COVID-19/blob/master/DL-us-mobility.ndjson): all mobility data in [NDJSON](https://github.com/ndjson/ndjson-spec) format.
- [**`DL-us-mobility-daterow.csv`**](https://github.com/descarteslabs/DL-COVID-19/blob/master/DL-us-mobility-daterow.csv): all mobility data in CSV format
- [**`DL-us-m50.csv`**](https://github.com/descarteslabs/DL-COVID-19/blob/master/DL-us-m50.csv): same data as `DL-us-mobility-daterow.csv`, but only with the `m50` field in time series format
- [**`DL-us-m50_index.csv`**](https://github.com/descarteslabs/DL-COVID-19/blob/master/DL-us-m50_index.csv): same data as `DL-us-mobility-daterow.csv`, but only with the `m50_index` field in time series format
- [**`DL-us-samples.csv`**](https://github.com/descarteslabs/DL-COVID-19/blob/master/DL-us-samples.csv): same data as `DL-us-mobility-daterow.csv`, but only with the `samples` field in time series format


### Field description

| Field | Description | Type | Example |
|-|-|-|-|
| `date` | Date on which the data was collected, in the format `M/D/YYYY` | string | 3/1/2020 |
| `country_code` | [ISO-2 code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) representing the country in which data was collected | string | US |
| `admin_level` | Level of [administrative unit] represented. Possible values are: <ul><li>`0` for country level</li><li>`1` for first-order [administrative unit]</li><li>`2` for second-order [administrative unit]</li></ul> | integer | 1 |
| `admin1` | Name of the first-order [administrative unit], sourced from [GeoNames]. Represents a state in the US. | string | Alabama |
| `admin2` | Name of the second-order [administrative unit], sourced from [GeoNames]. May be empty. Represents a county in the US. | string | Autauga County |
| `fips` | [FIPS code](https://www.census.gov/quickfacts/fact/note/US/fips) for the location represented | string | 1 |
| `samples` | Number of samples observed in the specified region | integer | 133826 |
| `m50` | Median of the max-distance mobility for all samples in the specified region | float | 8.331 |
| `m50_index` | Percent of normal `m50` in the region, with normal `m50` defined during `2020-02-17` to `2020-03-07` | integer | 79 |

[administrative unit]: https://en.wikipedia.org/wiki/Administrative_division#:~:text=For%20clarity%20and%20convenience%20the,or%20%22second%20administrative%20level%22.
[GeoNames]: https://www.geonames.org/


### Sample `ndjson` format

```json
{"cc": "US", "admin_level": 2, 
"admin1": "New Mexico", "admin2": "Santa Fe County", "fips": "35049", 
"date": ["2020-03-24", "2020-03-25", "2020-03-26"], 
"samples": [1337, 1292, 1331], 
"m50": [0.155, 0.278, 0.095], 
"m50_index": [2, 4, 1]}
...
```

### Sample `DL-us-mobility-daterow.csv` format

```csv
date,country_code,admin_level,admin1,admin2,fips,samples,m50,m50_index
2020-03-26,US,2,"New Mexico","Santa Fe County","35049",1331,0.095,1
...
```

### Sample `DL-us-m50.csv` time series format

```csv
country_code,admin_level,admin1,admin2,fips,2020-03-24,2020-03-25,2020-03-26
US,2,"New Mexico","Santa Fe County","35049",2,4,1
...
```


## Attribution

This data is licensed under a [Creative Commons Attribution 4.0
International License](https://creativecommons.org/licenses/by/4.0/), which requires attribution to "Descartes
Labs."  

Scientific publications may cite

> Warren, Michael S. & Skillman, Samuel W. "Mobility Changes in Response to COVID-19". _arXiv:2003.14228 [cs.SI]_, Mar. 2020. [arxiv.org/abs/2003.14228](https://arxiv.org/abs/2003.14228)

For online use, please link to Descartes Labs' website at
[descarteslabs.com/mobility](https://descarteslabs.com/mobility/).

See the [LICENSE](https://github.com/descarteslabs/DL-COVID-19/blob/master/LICENSE) for the terms of use for this data.
