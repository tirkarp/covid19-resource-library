# Camber Systems Social Distancing Reporter

[Camber Systems](https://cambersystems.com/about/) is a data company that leverages commercial data and technology to help democratic and academic institutions solve society's biggest problems. As part of the [COVID-19 Mobility Data Network](https://www.covid19mobility.org/), Camber Systems has developed a [social distancing reporter](https://covid19.cambersystems.com/) that provides a more accurate and actionable understanding of the effectiveness of social distancing and other policy interventions aimed at reducing or slowing the spread of COVID-19.

Data is sourced from multiple data sources collecting information about smartphone activity, location and movement. Camber Systems then continuously refine, clean, anonymize and carefully standardize said data to produce a complete socialization patterns within a county/tract.

Camber Systems is providing free access to their dataset for scientists, researchers, state and local officials for the purpose of making decisions and studying COVID-19. **You will need to email data@cambersystems.com, after which your project coordinator will have to sign the data use agreement.** Dataset will be available on Camber Systems' private [BigQuery](https://cloud.google.com/bigquery) warehouse.

Alternatively, we have downloaded the relevant datasets for our own use, available on [Box](https://purdue.app.box.com/folder/120554417769).

## Dataset

Camber Systems dataset provides a holistic view of whether the people in an area are appropriately social distancing, by measuring the entropy and radius of gyration. It can be used to show the movement between counties, the efficacy of shelter-in-place orders, and to quantify the effects of policy by examining how people change their behavior when changes are made. The dataset contains information _such as (non-exhaustive)_:

- mean number of stops a device made in a county/tract
- median radius of gyration in meters of devices which stayed in a county/tract overnight
- median uncorrelated Shannon entropy in meters of devices which stayed in a county/tract overnight
- number of transitions between counties/tracts of a device

Read the [official methodology](https://covid19.cambersystems.com/about/).

## Accessing Data

You can view the visualization of movement at Camber Systems' [website](https://covid19.cambersystems.com/).

For underlying dataset, please contact [Camber Systems](https://covid19.cambersystems.com/data-request/) at data@cambersystems.com. Alternatively, you can access the dataset on [Box](https://purdue.app.box.com/folder/120554417769). Last updated _August 12th, 2020_.

## Structure

On [Box](https://purdue.app.box.com/folder/120554417769), we have downloaded 3 files showing county-level data:

- **`county_movement_v4.json`** (~635 MB): movement of devices **within** a county
- **`county_transition_matrix_v4.csv`** (~760 MB): movement of devices **between** counties
- **`county_modal_matrix_v4.csv`** (~345 MB): time context for devices moving between counties

See the [official data dictionary](https://app.box.com/s/6y06k0yzgvvlj67svksdiil7xhv7xvpb) for field descriptions.

## Attribution

Refer the the official data use agreement signed.
