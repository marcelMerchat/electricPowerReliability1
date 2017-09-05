### Analysis of Electric Power Reliability
### US Department of Energy Compliance Reports

Published at:
http://rpubs.com/marcelMerchat/304554

### September 5, 2017
### Marcel Merchat


### Overview of Power Disruption Data

This report concerns SAIDA and SAIFI data for more than five hundred electric utility
companies that reported to the United States Department of Energy (DOE) according to
the IEEE-1366 standard in the three years from 2013-2015. We also discuss the event
time data found in Electric Disturbance reports for the years 2011-2016 which are filed
on Form OE-417 for larger power disruptions. Jordan Wirfs-Brock of Inside Energy
investigated the disturbance reports in August, 2014 and she maintains a website with
data over a 15-year period [1]. In this report, we investigate the reliability data
which was uniformly reported beginning in 2013 and the detailed event data which
became available starting in 2011. 

Raw Data

The raw data for this analysis are DOE annual reports that are Excel files.
There are two groups of files. The first group are reliability files with
SAIDA and SAIFI data; the second group consists of the detailed event time
data reported with Form OE-417. The reliability files named Reliability_2013,
Reliability_2014, and Reliability_2015 were obtained from the following
website within zip files named f8612013.zip, f8612014.zip, and f8612015.zip
at the following website.

##### https://www.eia.gov/electricity/data/eia861/index.html

The event time data is mined from files for Form OE-417 starting with the
year 2009. Even though the reliability files are more general, the time data
files begin with one named "2009_Annual_Summary.csv." These were summary files
for government officials concerned with major outages called "Electric
Disturbance Events" and have a special column for vandalism and cyber-attacks.
These Excel files were obtained from the following website: 

https://www.oe.netl.doe.gov/OE417_annual_summary.aspx.

Date and time information were converted to a time-series data type.


Notes:

[1] Jordan Wirfs-Brock of Inside Energy investigated the disturbance
reports in August, 2014 and she maintains a website with data over a 15-year period. 

http://insideenergy.org/2014/08/18/data-explore-15-years-of-power-outages/

[2] Code for this reproducible report is available at:

https://github.com/marcelMerchat/electricPowerReliabilty 

[3] Since these files are only available for manual downloading, the process began by
manually downloading them because DOE does not have an API or other method whereby
this can be accomplished automatically. Although a single program should ideally
accomplish everything and nothing should be manual for reproducible analysis.
After downloading, the files were placed in the project folder.

A second issue concerns the nature of the raw data files as Excel files.
The files were opened with Excel and re-saved as a comma-separated-values (csv)
text files without changes. The files are Excel reports and are not formatted as
data files.

[4] However, we can read Excel files directly by R programs using packages
such as RExcel. I did not do this for this preliminary report; instead, I opened
the files manually with Excel and re-saved them as exported comma-delimited text
files. Although involved to setup, Excel files should be automatically read but
this is perhaps unreasonable for a preliminary study such as this. From the
viewpoint of an R program, Excel files are equivalent to compressed binary files
and are handled in a similar manner except rather specialized package tools are
required to read and write to them directly.

[5] The raw Excel files and the corresponding csv files are included in my Github
repository for this project.

[6] Processing and Transforming the Raw Data

There are 1113 time records of power disturbances for the six years
from 2011 to 2016. Of these, 509 records report the numbers of affected
customers. The organized DOE reports made it possible to combine the data
over multiple years in the same tables. It might be useful to have similar
tables as dataset files that could be verified for rigorous studies beyond
the manual downloading and conversion to comma-separated format that were
performed to form them. 

#### THE END