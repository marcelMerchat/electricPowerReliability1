### Analysis of Electric Power Reliability
### US Department of Energy Compliance Reports

Published at:
http://rpubs.com/marcelMerchat/304554

### September 5, 2017
### Marcel Merchat


### Overview of Power Disruption Data

This report concerns SAIDA and SAIFI data for more than five hundred electric utility companies that reported to the United States Department of Energy (DOE) according to the IEEE-1366 standard in the three years from 2013-2015. We also discuss the event time data found in Electric Disturbance reports for the years 2011-2016 which were filed on Form OE-417 for larger power disruptions which were discussed by Jordan Wirfs-Brock of Inside Energy in August of 2014. She maintains a website with data over a 15-year period [1]. In this report, we investigate DOE reliability data which was uniformly reported beginning in 2013 along with more comprehensive event time data which became available starting in 2011. 

## Raw Data

[1] Jordan Wirfs-Brock of Inside Energy investigated the disturbance reports in August, 2014 and she maintains a website with data over a 15-year period. 

http://insideenergy.org/2014/08/18/data-explore-15-years-of-power-outages/

[2] Raw Data: There are two groups of raw data Excel files.

The first group are reliability files with SAIDA and SAIFI data. The files named Reliability_2013, Reliability_2014, and Reliability_2015 were taken from zip files named f8612013.zip, f8612014.zip, and f8612015.zip downloaded at this website.

https://www.eia.gov/electricity/data/eia861/index.html

The event time data is mined from files for Form OE-417 starting with the year 2011. Even though the reliability files are more general, the time data files begin with one named "2009_Annual_Summary.csv." These were summary files for government officials concerned with major outages called "Electric Disturbance Events" and have a special column where description such as vandalism and attack might be found. These Excel files were obtained from this website: 

[3] The raw data is not available as a dataset which means this report can only be considered preliminary as a single program should ideally accomplish everything for reproducible analysis. DOE does not have an API or other method whereby these files can be downloaded automatically. A recognized or approved data source is needed for a formal report. 

Thus the process began by manually downloading raw DOE files.  After downloading them, the files were placed in the project folder before opening with Excel and re-saving them as comma-separated-value (csv) text files without changes. 

[4] We can read Excel files directly by R programs using packages such as RExcel. I did not do this for this preliminary report. Although somewhat involved to setup, Excel files could be automatically read but this is perhaps unreasonable for a preliminary study such as this. From the viewpoint of an R program, Excel files are equivalent to compressed binary files and are handled in a similar manner. Rather specialized package tools read and write to them directly.

[5] The raw Excel files and the corresponding csv files are included in my Github repository for this project. Independent investigators would generally work to verify these files as reliable. 

[6] Processing and Transforming the Raw Data

The reliability reports can be converted directly by R into data frame with twenty-two columns. There are 966 utility company records. Column-13 indicates whether or not power outages are recorded automatically. As we discuss in the report, we included only records for automatic recording which reduced the size of the study from 966 to 306 utilities. Figure-8 shows how automatic detection affects reported data. 

There are 1113 time records of power disturbances for the six years from 2011 to 2016 in the OE-417 event reports. Of these, 509 records report the numbers of affected customers. Date and time information were converted to a time-series data type in order to compute the duration of power outages and lost customer hours. There are many records for vandalism or attacks for which there is little or no effects on customers. The organized DOE reports made it possible to combine the data over multiple years in the same tables.

Figure-8 shows how automatic detection in Column-13 affected reported data. As discussed in the report, only records for automatic recording were used which reduced the size of the study to about 300. 

### Prediction Table for Testing Group

[7] The code for this reproducible report is available at https://github.com/marcelMerchat/. 

#### THE END