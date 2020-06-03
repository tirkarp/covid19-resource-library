# Human traffic data from Yahoo! Japan

This dataset contains the index of the number of people entering and leaving a prefecture on a given day in a month in 2020, as compared to those in 2019.

The original source file is in Excel format (`.xlsx`), please run the script below to convert the Excel files to CSV, if not already done so.
```
pip3 install pandas xlrd
python3 getsheets.py come_in_index_japan.xlsx go_out_index_japan -f csv
```

