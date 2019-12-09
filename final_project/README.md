# [Final project](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A7:_Final_project_report)

Data 512  
Tara Wilson  
Autumn quarter 2019  

## Project goal

The goal of this assignment is to practice reproducible research and effectively communicate findings.
This research is about NCAA college football, specifically which factors influence attendance. This 
work looks into the interaction several features have on game attendance from the 2012-2018 seasons.

Human-centered data science is work designed to address human need (Week 1 Lecture Slides). The 
ability to understand what factors make or deter fans from attending college football games has 
the power to make the experience better for everyone. Games are more fun to attend, programs make 
more money and players enjoy playing more when the stadium is full. Using data to determine what 
the driving factors are can help identify the opportunities to improve the experience across the 
board.

## Project motivations

As a huge college football fan, I wanted to do my project on a topic I care a lot about and 
in an area that I already have domain knowledge in. Attendance is a huge part of revenue 
for a university, but is also important for the program as it helps the school come across 
as well represented and helps finance the athletics department, so I thought it would be 
interesting to explore in depth.  

College football attendance has been dropping recently, and is in a 22-year low, with many 
pinning the decline on technology such as
[TechCrunch](https://techcrunch.com/2019/09/08/as-college-football-attendance-slumps-new-ways-to-ticket-may-hold-an-answer/). 
Others have been blaming the decline on the use of cell phones like 
[front office sports](https://frntofficesport.com/college-football-attendance/). Still others pin 
this decrease on a change in stadium capacity since "from 2004 to 2018, the average stadium 
capacity has fallen over 2,000 - almost 2,400 seats" noting that stadiums like Ohio State have 
altered designs to focus on more luxury seats per [NPR](https://www.npr.org/2019/08/24/753962604/attendance-drops-for-college-football). 
[Off Tackle Empire](https://www.offtackleempire.com/2019/7/24/20707199/millennials-terrible-phones-pat-fitzgerald-college-football-attendance-decline-big-ten-media-days) 
cites kickoff times and team success as possible factors that influence attendance. 

As of 2018, it was the "seventh time in the last eight years that attendance has declined" as reported by 
[FunBuzz](https://fanbuzz.com/college-football/cfb-attendance-2019/). Clearly, the phenomenon 
of declining attendance is evident but there does not appear to be a clear and agreed upon cause. 
This made me want to investigate and see if I could uncover any trends over the past 7 seasons. 
While the dataset I will be using does not include pricing information, technology use or seat 
type data, it will allow me to uncover how stadium capacity, match-up quality and weather factor 
into attendance. It is most likely that many factors are simultaneously contributing to the 
decline of attendance so identifying some of these compounding reasons is a welcome challenge. 

Since I knew this was a problem that has been identified, I was really interested in doing some 
numerical analysis to see if I could find any correlations with dropping attendance. I wanted to 
explore several varied aspects of this since many ideas have been tossed around in media outlets 
of what is causing this decline. Identifying factors that either do or do not appear to be tied 
to the number of people attending games will help build a more comprehensive understanding of 
what impacts NCAA football attendance and thus help schools reverse this trend.

## Project conclusions

This analysis concludes that the stadium size, home and away team success, and non-conference match-ups
have the largest positive influences on game attendance. This study also finds that temperature and precipitation
have essentially no implications on game attendance. The files in this repository
include data visualizations, stastistical analysis and descriptions of my findings and their respective implications
along with discussion of the limitations of and potential future improvements to this study. 

## Table of contents

* raw_data/
    * games_endpoint_2012.json
    * games_endpoint_2013.json
    * games_endpoint_2014.json
    * games_endpoint_2015.json
    * games_endpoint_2016.json
    * games_endpoint_2017.json
    * games_endpoint_2018.json
    * rankings_endpoint_2012.json
    * rankings_endpoint_2013.json
    * rankings_endpoint_2014.json
    * rankings_endpoint_2015.json
    * rankings_endpoint_2016.json
    * rankings_endpoint_2017.json
    * rankings_endpoint_2018.json
    * venues_endpoint.json
* processed_data/
    * seasons_2012-2018_attendance_data.csv
* project_deliverables/
    * [A4_final_project_proposal.md](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A4:_Final_project_proposal)
    * [A5_final_project_plan.md](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A5:_Final_project_plan)
    * final_presentation_deck.pptx
    * [A6_final_project_presentation.pdf](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A6:_Final_project_presentation)
* visuals/
    * home_team_rank_indicator.jpg
    * away_team_ranked_indicator.jpg
    * conference_indicator.jpg
    * max_temp_vs_attendance.jpg
    * min_temp_vs_attendance.jpg
    * rain_indicator.jpg
* data_analysis.ipynb
* data_collection.ipynb
* LICENSE

### Data sources

#### College football data

I plan to use the College Football database, aggregated by Bill Radjewski. The dataset contains 
information about most all aspects of college football including game data, drive data, play by 
play data, team data, player data, coach data, venue data and player/game statistics. This 
dataset has a good mix of categorical and quantitative data which will help give me good 
experience with both. 

The data is available [here](https://github.com/BlueSCar/cfb-database), and I will access it 
using [this API](https://api.collegefootballdata.com/api/docs/?url=/api-docs.json#/). The data 
is made available under a [standard MIT License](https://github.com/BlueSCar/cfb-database/blob/master/LICENSE).

#### Weather data 

I will also be using weather data from [NOAA Weather API](https://www.noaa.gov/weather). 
This data is available under public domain. More specifically, I will be gathering temperature 
and precipitation information to supplement the game data.

More information on data collection can be found in the data_collection.ipynb file.

### Analysis scripts

#### Data analysis

This iPython Notebook analyzes the data in processed_data/seasons_2012-2018_attendance_data.csv.
It lists my hypotheses for the factors that influence attendance at college football games. 
It creates visualizations and tables for the data and calculates corresponding statistics to 
address all of the hypotheses. It also contains conclusions and a detailed discussion of the findings
as well as acknowledgement of study limitations and suggestions for future work.

#### Data collection

This iPython Notebook makes the API calls from the above mentioned sources, aggregates and cleans the data. 
This file also includes the feature engineering for variables used in the analysis. Generates the .json
files from API calls and saves final dataset to processed_data/seasons_2012-2018_attendance_data.csv.

### Output files

#### Resulting dataset for analysis (seasons_2012-2018_attendance_data.csv)

|   column name        |   description  |
|:---------------------|----------------|
|attendance            |Count of attendees for game |
|away_conference       |Conference abbreviation for away team |
|away_line_scores      |Betting line for the away team |
|away_points           |Number of points scored by the away team during the game |
|away_team             |Name of away team |
|conference_game       |Boolean indicator of if home and away team are from the same conference |
|home_conference       |Conference abbreviation for home team |
|home_line_scores      |Betting line for the home team |
|home_points           |Number of points scored by the home team during the game |
|home_team             |Name of home team |
|id                    |Unique ID for the game |
|neutral_site          |Boolean indicator of if the game took place not at either team's stadium |
|season                |Year the game took place |
|season_type           |Indicator of regular or post season game |
|start_date            |Start date of the game (month/day/year) |
|venue                 |Venue name |
|venue_id              |Unique ID for the venue |
|week                  |Week # of the season |
|capacity              |Number of seats in the stadium |
|city                  |City of the stadium location |
|country_code          |Country code of the stadium location |
|dome                  |0, 1 indicator of if the stadium is indoor dome |
|elevation             |Elevation of the stadium (m) |
|grass                 |0, 1 indicator of if the stadium has real grass or not |
|location              |Latitude and longitude of stadium location {x: coord, y: coord} |
|name                  |Name of the stadium |
|state                 |State abbreviation of the stadium location |
|year_constructed      |Year the stadium was constructed |
|zip                   |Zip code of the stadium location|
|attendance_percentage |Attendance / capacity for the game |
|home_team_ranked_ind  |Indication of if home team was ranked the week of the game in the AP poll (1 if yes, 0 if no) |
|away_team_ranked_ind  |Indication of if away team was ranked the week of the game in the AP poll (1 if yes, 0 if no) |
|rain                  |Amount of rain in the venue area on the day of the game |
|max_temp              |Maximum temperature in the venue area on the day of the game (F) |
|min_temp              |Minimum temperature in the venue area on the day of the game (F) |
