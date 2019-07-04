# Network Traffic Exploration
A weekend project exploring network traffic from anonymous organization, donated by one of my clients.
## Raw Data
The file report.csv is captured from MikroTik Network router, recording the network traffic per each user session.
![Raw Data](https://github.com/Ozeidi/NetworkTraffic/blob/master/imgs/Raw%20Data.png)
### Data Dictionary

Column 1 : User : Unique ID per user  
Column 2 : Profile : Type of user profile (Public/Private)  
Column 3 : Price : For profiles that has a specific price rate.  
Column 4 : : Time/Date when the user profile was created (Redundent Feature)  
Column 5 : : Bandwidth limit.  
Column 6 : : Start of the session.  
Column 7 : : End of the session.  
Column 8 : : Connection session duration.  
Column 9 : Download : Size of download traffic.  
Column 10: Upload : Size of upload traffic.  
NOTE: Download and Upload Traffic get reported at various units (KiB, MiB, GiB)
## Objective 
I the breif RMarkdown file, we try to explore the patterns of the network trafic in the organization. By doing so, we intend to tackle following questions:
1. How does the traffic distribute along hours of the day and along days of the week?
2. Are there any abnormal patterns we can highlight?

## Data Preparation
The raw data is organized in a row per session format, where each connection session has it's associated start/end time and respective upload/download traffic.  
To conduct any type of timeseries analysis, we need to convert the raw data into a time-series form. We do so by populating an hourly timeseires from session start to end time with the total traffic split per hours of connection.  

![Raw Data To Timeseries](https://github.com/Ozeidi/NetworkTraffic/blob/master/imgs/Raw%20Data%20to%20timeseries.png)
Before conducting the above transformation, we have a series of preparation steps:
1. Unify the Upload and Download units to be in Gigabytes.
2. Convert the Timestamps in R-recognized form.
3. Convert Timestamps from MikroTik UTC timezone into Oman Time Zone.
4. Combine Up/Down Traffic into Total Traffic variable

## Insights
We use the the previously transformed dataset to genereatr a set of informative visulaisations.
1. Total Network Traffic per hour of the day: This shows expected pattern of increased activity during the working hours from 7am - 2pm.

2. Mean Network Traffic Faceted Plot: This plot shows the mean network traffic hour of the day for each weekday. Interestingly there was a presistent trough in traffic around 10am daily. Up on further inspection this trough happens to reflect employees habit of having breakfast/coffee every day around the same time.

