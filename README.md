# Changelog
## Version 1.00 28-Jan-2021
Initial release.

## Version 1.0.2 25-Feb-2020
* print_prod_CPU.to_csv to print_stg_CPU.head(29).to_csv to only print the 30 PROD servers for CPU util
* print_prod_Mem.to_csv to print_stg_Mem.head(29).to_csv to only print the 30 PROD servers for Mem util
* print_stg_CPU.to_csv to print_stg_CPU.head(30).to_csv to only print the 30 STG servers for CPU util
* print_stg_Mem.to_csv to print_stg_Mem.head(30).to_csv to only print the 30 STG servers for Mem util
* Organized the directories
* Output file now consolidated in the /weekly_output directory
* Added cleanup commands such as removing additional column and resetting the index number in the final output
* Combined outputs for prod and staging environments
* Combined all .csv outputs to multiple sheets in one .xlsx file
* Renamed python script to run-me.ipynb
===
# Preparation
## Files needed:
1. envMem.csv - from GoogleSpreadSheet
2. envCPU.csv - from GoogleSpreadSheet
3. prodMem.csv - from Splunk (weekly)
4. prodCPU.csv - from Splunk (weekly)
5. stgCPU.csv  - from Splunk (weekly)
6. stgMem.csv - from Splunk (weekly)
7. prodFS.csv - from Splunk (weekly)
---
## Links
* [DPA Environment](https://docs.google.com/spreadsheets/d/1Ll7-mdb8tsGUKIDYJ-dMEBmydxXf24krk8J7r1RIUog/edit#gid=588246582)
* [Splunk (DPA PROD/Staging 2)](http://10.69.81.41:8000/en-US/app/splunk_app_for_linux_Infrastructure/dashboards)
---
## Helpful Commands
* print(mem_df.loc[[20]]) # printing x row
* envMem_df.tail(10)
* mem_df.tail(10)
* mem_df = df.sort_values(by=['Column_name'], ascending=True) # to sort by column
* DPAenv_df.columns # for reference to check which column to join from DPAenv
* mergedData.to_csv('filename') # for exporting
* mergedData.to_csv('filename', index=False) # to remove the index column
---
## Legend
* FS - File System
* df - data file (.csv, xlx, etc)
* env - environment (official .csv Environment file from google sheets)
---
# How To Use
1. Rename/save the .csv files to prodMem.csv, stgMem.csv, prodCPU.csv, stgCPU.csv, prodFS.csv
2. Get Environment files from Google Sheet and name them as envMem.csv, envCPU.csv & envFS.csv
3. Place them in Jupyter Notebook dir (./DPA_report/sources/)
4. Run each boxes, from top to bottom, containing the script by selecting each of them and hitting CTRL + Enter.

