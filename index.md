---
layout: default
---


After downloading the splunk’s dmg file from their official website, I ran a hash check on the file to make ensure its integrity.

![1](1.png)


I double-clicked the installer and followed the instructions. I’ve provided screenshots below to highlight every time I was prompted.

![2](2.png) | ![3](3.png)

![4](4.png) | ![5](5.png)

![6](6.png) | ![7](7.png)

![8](8.png) | ![9](9.png)

![10](10.png) | ![11](11.png)

![12](12.png)


Created a username and password for my admin splunk account and started the web application.

![13](13.png) | ![14](14.png)

![15](15.png)


Then I signed in and immediately ingested the log data from my laptop.

![16](16.png) | ![17](17.png)

![18](18.png) | ![19](19.png)

![20](20.png) | ![21](21.png)


Then I used the “Search & Reporting” app to search for the top domains with the most failed processes with the command:
```
failed | top limit=10 Domain
```
Then I used the visualisation feature create a pie chart to represent the information and saved it as a report to later add it to a Dashboard. From this visualisation, I can determine that NSCocoa Domain had the most failed processes which willed a further investigation.

![22](22.png) | ![23](23.png)

![24](24.png)


Then I used the “Search & Reporting” app to search for the status of processes on the internal system with the command:
```
index=“_internal” | top limit=6 status
```
Then I used the visualisation feature create a bar chart to represent the information and saved it as a report to later add it to a Dashboard. From this visualisation, over 90% of the processes have a  status of 200 which signifies a smooth running system.

![25](25.png) | ![26](26.png)

![27](27.png)


Then I used the “Search & Reporting” app to search for the actions taken on the config data with the command:
```
index=“_configtracker” | top limit=2 “data.action””
```
Then I used the visualisation feature create a pie chart to represent the information and saved it as a report to later add it to a Dashboard. From the pie chart, I can determine that only 7% of the config data was updated.

![28](28.png) | ![29](29.png)

![30](30.png)


I Created a new dashboard in classic mode.

![31](31.png) | ![32](32.png)


Then I imported all three reports into the dashboard.

![33](33.png) | ![34](34.png)

![35](35.png) | ![36](36.png)


Finally, I cloned my dashboard in dashboard studio in grid mode for a better presentation.

![37](37.png) | ![38](38.png)

![39](39.png) | ![40](40.png)
