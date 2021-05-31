# <div align="center"> Merge CSV Files with Jupyter Notebook </div>
<p align="center"> <img src="https://i2.wp.com/learn.onemonth.com/wp-content/uploads/2019/07/image3-1.png?fit=756%2C277&ssl=1" width="350"> </p>

---
## Changelog

### [v2.0.0](run-me-v2.0.0.ipynb) (31-05-2021)
#### Added
* Added dropping of rows with _NaN_ values on the "Used" column.
* Added more "PRINT TO SCREEN" options.

#### Changed
* Changed environment file from envCPU.csv to envcpu.csv.
* Changed environment file from envMem.csv to envmem.csv.
* Changed environment file from envFS.csv to envfs.csv.
* Changed source file from prodMem.csv to prodmem.csv.
* Changed source file from stgMem.csv to stgmem.csv.
* Changed source file from prodCPU.csv to prodcpu.csv.
* Changed source file from stgCPU.csv to stgcpu.csv.
* Changed source file from prodCPU.csv to prodcpu.csv.
* Removed `.head()` option in when exporting to individual csv files as it is no longer required.
* Compiled all lines of code to one page / one jupyter notebook row.
* Backed previous version to `./old-scripts/run-me-v1.0.2.ipynb`.

### [v1.0.2](./old-scripts/run-me-v1.0.2.ipynb) (25-02-2021)

#### Changed
* print_prod_CPU.to_csv to print_stg_CPU.head(29).to_csv to only print the 30 PROD servers for CPU util.
* print_prod_Mem.to_csv to print_stg_Mem.head(29).to_csv to only print the 30 PROD servers for Mem util.
* print_stg_CPU.to_csv to print_stg_CPU.head(30).to_csv to only print the 30 STG servers for CPU util.
* print_stg_Mem.to_csv to print_stg_Mem.head(30).to_csv to only print the 30 STG servers for Mem util.
* Organized the directories.
* Output file now consolidated in the /weekly_output directory.
* Added cleanup commands such as removing additional column and resetting the index number in the final output.
* Combined outputs for prod and staging environments.
* Combined all .csv outputs to multiple sheets in one .xlsx file.
* Renamed python script to run-me.ipynb.

### v1.0.0 (28-01-2021)
* Initial release.


---
## Preparation
### Requirements
* python3
* jupyter notebook
* pandas
* xlsxwriter

### Files Needed
1. envMem.csv - from DPA Environment (once)
2. envCPU.csv - from DPA Environment (once)
3. prodmem.csv - from Splunk (weekly)
4. prodcpu.csv - from Splunk (weekly)
5. stgcpu.csv  - from Splunk (weekly)
6. stgmem.csv - from Splunk (weekly)
7. prodfs.csv - from Splunk (weekly)

### Links
* [DPA Environment](https://docs.google.com/spreadsheets/d/1Ll7-mdb8tsGUKIDYJ-dMEBmydxXf24krk8J7r1RIUog/edit#gid=588246582)
* [Splunk (DPA PROD/Staging 2)](http://10.69.81.41:8000/en-US/app/splunk_app_for_linux_Infrastructure/dashboards)

### Helpful Commands
* print(mem_df.loc[[20]]) # printing x row
* envMem_df.tail(10)
* mem_df.tail(10)
* mem_df = df.sort_values(by=['Column_name'], ascending=True) # to sort by column
* DPAenv_df.columns # for reference to check which column to join from DPAenv
* mergedData.to_csv('filename') # for exporting
* mergedData.to_csv('filename', index=False) # to remove the index column

### Legend
* FS - File System
* df - data file (.csv, xlx, etc)
* env - environment (official .csv Environment file from [DPA Environment](https://docs.google.com/spreadsheets/d/1Ll7-mdb8tsGUKIDYJ-dMEBmydxXf24krk8J7r1RIUog/edit#gid=588246582)

---
## How To Use
1. Rename/save the .csv files to prodmem.csv, stgmem.csv, prodcpu.csv, stgcpu.csv, and prodfs.csv.
2. Get Environment files from [DPA Environment](https://docs.google.com/spreadsheets/d/1Ll7-mdb8tsGUKIDYJ-dMEBmydxXf24krk8J7r1RIUog/edit#gid=588246582) and name them as envMem.csv, envCPU.csv & envFS.csv.
3. Place them in Jupyter Notebook dir (./DPA_report/sources/).
4. Run each boxes, from top to bottom, containing the script by selecting each of them and hitting <kbd>CTRL</kbd> + <kbd>Enter</kbd>.
