# PlaceIQ Exposure Indices

[PlaceIQ](https://www.placeiq.com/) is a company that offers location intelligence to better understand customer behaviors and make an informed business and marketing decisions. 

A group of researchers at UC Berkeley have calculated a set of indices describing exposure on the basis of smartphone movements. They are derived from anonymized, aggregated smartphone movement data provided by PlaceIQ. They are making this dataset publicly available via their [GitHub repo](https://github.com/COVIDExposureIndices/COVIDExposureIndices). 

## Datasets

COVID Exposure Indices measures (potential) human exposure varying across locations and time within the United States. Data used to calculated the indices are sourced from PlaceIQ data that describes smartphones _pinging_ in a given geographic unit in a given day. They are divided into two categories:

- **Location Exposure Indices (LEX)**: among smartphones that _pinged_ in a given location today, what share of those devices _pinged_ in each location at least once during the previous 14 days? Read the [methodology](https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/0e470e19026b2341ec6af16e4b853ce899964415/documentation/LEX.pdf).
- **Device Exposure Indices (DEX)**: the exposure of devices residing in a given location. The daily exposure of a device `i` is defined as the number of distinct devices that visit any commercial venue that device `i` visits on that day. Read the [methodology](https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/0e470e19026b2341ec6af16e4b853ce899964415/documentation/DEX.pdf).

Read the [official description](https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/master/README.md). 

Data is updated every weekday, and is available back till _January 7th, 2020_.
