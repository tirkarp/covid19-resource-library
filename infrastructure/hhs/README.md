# U.S. Department of Health and Human Services (HHS) Patient Impact and Hospital Capacity

The U.S. Department of Health and Human Services (HHS) curates [a series of datasets](https://healthdata.gov/search/type/dataset?query=covid-19&sort_by=changed&sort_order=DESC) related to COVID-19 from federal, state, and local agencies all around the country. 

Among the data streams include data recorded by HHS themselves. This data is derived from reports with facility-level granularity across two main sources:

- [HHS TeleTracking](https://www.teletracking.com/)
- reporting provided directly to HHS Protect by state/territorial health departments on behalf of their healthcare facilities

## Dataset

We found two main datasets sourced from HHS related to COVID-19:

- [**Reported Patient Impact and Hospital Capacity**](#reported-patient-impact-and-hospital-capacity): timeseries reported figures on hospital utilization across states
- [**Estimated Patient Impact and Hospital Capacity**](#estimated-patient-impact-and-hospital-capacity): timeseries estimated figures on hospital utilization across states

## Accessing Data

You can find and download the datasets on the [HHS website](https://healthdata.gov/search/type/dataset?query=covid-19&sort_by=changed&sort_order=DESC). Specifically:
- the [**reported hospital capacity** dataset](#reported-patient-impact-and-hospital-capacity) is found at this [link](https://healthdata.gov/dataset/covid-19-reported-patient-impact-and-hospital-capacity-state)
- the [**estimated hospital capacity** dataset](#estimated-patient-impact-and-hospital-capacity) is found at this [link](https://healthdata.gov/dataset/covid-19-estimated-patient-impact-and-hospital-capacity-state)

Alternatively, you can access each dataset in the [`dataset/`](dataset/) directory.

## [Reported Patient Impact and Hospital Capacity](https://healthdata.gov/dataset/covid-19-reported-patient-impact-and-hospital-capacity-state)

HHS provides the [latest values](https://healthdata.gov/dataset/covid-19-reported-patient-impact-and-hospital-capacity-state) of utilization **reported** by each healthcare facility in every state within the last four days. Values represented include:

- inpatient bed capacity
- inpatient bed utilization
- inpatient bed utilization for patients with COVID-19
- ICU bed capacity
- ICU bed utilization

### Structure

The reported hospital capacity is recorded in a single `.csv` file. Field descriptions can be found in the [data dictionary](https://healthdata.gov/covid-19-reported-patient-impact-and-hospital-capacity-state-data-dictionary).


## [Estimated Patient Impact and Hospital Capacity](https://healthdata.gov/dataset/covid-19-estimated-patient-impact-and-hospital-capacity-state)

HHS provides [state-aggregated data](https://healthdata.gov/dataset/covid-19-estimated-patient-impact-and-hospital-capacity-state) for **projected** patient impact and hospital utilization during the period of COVID-19 pandemic. Dataset contains similar information to the [reported hospital capacity](#reported-patient-impact-and-hospital-capacity).

### Structure

Projection is divided into three different files (in the [`dataset/`](dataset/):

- [**`inpatient-beds.csv`**](dataset/inpatient-beds.csv): timeseries number and percentage of inpatient beds occupied in each state
- [**`covid19-beds.csv`**](dataset/covid19-beds.csv): number and percentage of inpatient beds occupied by COVID-19 patients
- [**`icu-beds.csv`**](dataset/icu-beds.csv): number and percentage of ICU beds occupied in each state
