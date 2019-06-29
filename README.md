# Network Traffic Exploration
A weekend project exploring network traffic from anonymous organization, donated by one of my clients.
## Raw Data
The file report.csv is captured from MikroTik Network router, recording the network traffic per each user session.
![Raw Data](https://github.com/Ozeidi/NetworkTraffic/blob/master/imgs/Raw%20Data.png)
### Data Dictionary
Column 1: User : Unique ID per user 
Column 2: Profile : Type of user profile (Public/Private)
Column 3: Price : For profiles that has a specific price rate
Column 4: : Time/Date when the user profile was created (Redundent Feature)
Column 5: : Bandwidth limit
Column 6: : Start of the session.
Column 7: : End of the session.
Column 8: Download : Size of download traffic
Column 9: Upload : Size of upload traffic

## Code 
I the breif RMarkdown file, we try to explore the patterns of the network trafic in the organization. By doing so, we intend to tackle following questions:
1. How does the traffic distribute along hours of the day and along days of the week?
2. Are there any abnormal patterns we can highlight?

