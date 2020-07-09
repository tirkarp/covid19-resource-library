# PlaceIQ Exposure Indices

[PlaceIQ](https://www.placeiq.com/) is a company that offers location intelligence to better understand customer behaviors and make an informed business and marketing decisions. 

A group of researchers at UC Berkeley have calculated a set of indices describing exposure on the basis of smartphone movements. They are derived from anonymized, aggregated smartphone movement data provided by PlaceIQ. They are making this dataset publicly available via their [GitHub repo](https://github.com/COVIDExposureIndices/COVIDExposureIndices). 

## Datasets

COVID Exposure Indices measures (potential) human exposure varying across locations and time within the United States. Data used to calculated the indices are sourced from PlaceIQ data that describes smartphones _pinging_ in a given geographic unit in a given day. They are divided into two categories:

- [**Location Exposure Indices (LEX)**](#location-exposure-indices-lex): among smartphones that _pinged_ in a given location today, what share of those devices _pinged_ in each location at least once during the previous 14 days? Read the [methodology](https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/0e470e19026b2341ec6af16e4b853ce899964415/documentation/LEX.pdf).
- [**Device Exposure Indices (DEX)**](#device-exposure-indices-dex): the exposure of devices residing in a given location. The daily exposure of a device `i` is defined as the number of distinct devices that visit any commercial venue that device `i` visits on that day. Read the [methodology](https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/0e470e19026b2341ec6af16e4b853ce899964415/documentation/DEX.pdf).

Read the [official description](https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/master/README.md). 

Data is updated every weekday, and is available back till _January 7th, 2020_.

## How to access data

LEX and DEX datasets are available on the research group's GitHub repo, or in the [`dataset`](dataset/) directory. Last updated _June 11th, 2020_.

## Location Exposure Indices (LEX)

LEX is a dataset that describes the precentage of devices that _pinged_ in each location at least once during the previous 14 days, that are still _pinging_ today. Read the [methodology](https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/0e470e19026b2341ec6af16e4b853ce899964415/documentation/LEX.pdf).

### Structure

LEX data is organized at a county-level and state-level, each having its own file _per day_. Each file is a `.csv` file containing a square matrix describing percentage of _ping_ from each location now, to other locations in the previous 14 days. For example, the state-level data will contain:

| `STATE_PRE` | AK | AL | AR | AZ | CA | CO | CT | ... |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| **AK** | ... | ... | ... |  |  |  |  |  |
| **AL** | ... | ... | ... |  |  |  |  |  |
| **AR** | ... | ... | ... |  |  |  |  |  |
| **AZ** | : | : | : |  |  |  |  |  |
| **CA** |  |  |  |  |  |  |  |  |
| **CO** |  |  |  |  |  |  |  |  |
| **CT** |  |  |  |  |  |  |  |  |
| **:** |  |  |  |  |  |  |  |  |

where the geographic identifiers for state-level data are two-letter [postal abbreviations](https://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations). The geographic identifiers for county-level data are five-digit [FIPS code](https://transition.fcc.gov/oet/info/maps/census/fips/fips.txt). 

Read the [official usage notes](https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/master/documentation/LEX_notes.md).

In addition, the files `state_devicescount.csv` and `county_devicescount.csv` are supplied for more information about the total number of devices that _ping_ per day.

`csv` files may come compressed in `.gz` format. To unzip, run `gunzip file-name.csv.gz`.
