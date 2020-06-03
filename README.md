# COVID-19 Datasets

Run the following command to clone this repository
```
git clone --recursive https://github.com/tirkarp/covid19.git
```

To pull latest changes from all submodules, run:
```
git submodule update --remote --merge
```

## Source Index
General sources of data that may be of interest:

| Source | Description | Tags |
|-|-|-|
| [Tableau Public](https://public.tableau.com/en-us/s/covid-19-viz-gallery) | Tableau visualizations on various aspects of COVID, from which we can obtain sources. | `Catalog` |
| [MIDAS](https://midasnetwork.us/covid-19/#resources) | Catalog of COVID-19 datasets, along with pubished estimates of parameters such as basic reproduction number. | `Catalog`, `Parameters` |
| [AWS Data Lake](https://aws.amazon.com/blogs/big-data/a-public-data-lake-for-analysis-of-covid-19-data/) | Centralized repository of datasets related to the spread of COVID-19. | `Catalog` |

## Tag Descriptions
- `Catalog`: a gallery of sources from which we can pull datasets
- `Parameters`: contains published estimates of parameters e.g. basic reproduction number
