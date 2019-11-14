# A5: Final Project Plan
### Data 512
### November 8, 2019
### Tara Wilson

## 1. Motivation/problem statement

As a huge college football fan, I wanted to do my project on a topic I care a lot about and in an area that I already have domain knowledge in. Specifically, I think it would be interesting to look at factors driving game attendance. Attendance is a huge part of revenue, but is also important for the program as it helps the school come across as well represented. I think some factors included in the dataset, such as venue capacity, success of team and challenge of opponent, all of which can be found in this same dataset, have significant impact on attendance. If I wanted to bring in additional data to create more of a challenge I think looking at gameday weather would produce interesting analysis as well.

I want to strengthen my data communication skills through this assignment – both in terms of reproducible code and in terms of analysis and visualizations. I think sports data poses an intriguing challenge since there is a specific set of vocabulary in the space that fans are used to so I will try to balance this while also making my project interpretable to the general public. I think this is an important aspect of human centered data science, as analysis that cannot be understood by the intended audience does not make for successful research. I want to strengthen my feature engineering skills as well so that I can practice generating fields such as indicators. I think the vast amounts of different type of information in this dataset will help me answer the questions I hope to, as well as provide an opportunity to improve my Python and reproducible research skills.

Human-centered data science is designed to address human need (Week 1 Lecture Slides). The ability to understand what factors make or deter fans from attending college football games has the power to make the experience better for everyone. Games are more fun to attend, programs make more money and players enjoy playing more when the stadium is full. Using data to determine what the driving factors are can help identify the opportunities to improve the experience across the board.


## 2. Data used

I plan to use the College Football database, aggregated by Bill Radjewski. The dataset contains information about most all aspects of college football including game data, drive data, play by play data, team data, player data, coach data, venue data and player/game statistics. This dataset has a good mix of categorical and quantitative data which will help give me good experience. 

The data is available [here](https://github.com/BlueSCar/cfb-database), and I will access it using [this API](https://api.collegefootballdata.com/api/docs/?url=/api-docs.json#/). The data is made available under a [standard MIT License](https://github.com/BlueSCar/cfb-database/blob/master/LICENSE).

This data is relevant to my problem statement because it covers most all aspects of college football. There should be ample information to answer the questions I choose, as well as room to explore additional factors if desired. The pertinent data columns for my research are:  

| Column name | API         |
|-------------|-------------|
| start_date  | game |
| neutral_site| game |
| conference_game|game|
| attendance  | game |
| capacity    | venue|
| location    | venue|
| home_team   | game |
| season_type | game |
| away_team   | game |
| rank        | rank |

In terms of ethical concerns, the data does contain identifiable information on athletes such as height, weight, and hometown. However, I believe this is a side effect of playing NCAA football as this information can easily be found on team rosters, scouting websites, etc. so I do not believe there are any real privacy issues. 

I will also be using weather data from [NOAA Weather API](https://www.noaa.gov/weather). This data is available under public domain.


## 3. Unknowns and dependencies

My biggest concern is the availability of the dataset since there are no guarantees about up-time, etc. To combat this, I am planning to store local copies of the data I will use for the analysis once I have completed the API calls. 

I checked a subset of the data and it looks correct and complete but another potential roadblock would be incomplete sections of the data that would be necessary for a total analysis causing me to have to pivot. 

Since the data is so vast and in an area I am curious about I also need to be cognizant of scope creep and ensure I stay answering my proposed questions only.

Additionally, there is a dependency on being able to retrieve accurate weather data for the records to complete my desired set of questions.


## 4. Research questions and/or hypotheses

**Research Question:** What factors influenced attendance rates at College Football games over the 2012 - 2018 seasons?
**Hypotheses:**
* H1. Larger stadium capacities have higher percentages of attendance than stadiums that can accommodate less people.
* H2. The higher the quality of the home team for the game week, the higher the percentage of attendance.
* H3. The higher the quality of the away team for the game week, the higher the percentage of attendance.
* H4. Conference matchups have higher percentages of attendance than non-conference games.
* H5. Games with a temperate kickoff temperature will have higher percentages of attendance than those with extremely high or extremely low temperatures.
* H6. Games without rain will have higher percentages of attendance than those with rain.

Note: The last 2 hypotheses are conditional on being able to successfully find appropriate weather data.

## 5. Background and/or Related Work

College football attendance has been dropping recently, and is in a 22-year low, with many pinning the decline on technology [TechCrunch](https://techcrunch.com/2019/09/08/as-college-football-attendance-slumps-new-ways-to-ticket-may-hold-an-answer/). Others have been pinning the decline on the use of cell phones [front office sports](https://frntofficesport.com/college-football-attendance/). Still others pin this on a change in stadium capacity since "from 2004 to 2018, the average stadium capacity has fallen over 2,000 - almost 2,400 seats" noting that stadiums like Ohio State have changed to focus on more luxury seats [NPR](https://www.npr.org/2019/08/24/753962604/attendance-drops-for-college-football). [Off Tackle Empire](https://www.offtackleempire.com/2019/7/24/20707199/millennials-terrible-phones-pat-fitzgerald-college-football-attendance-decline-big-ten-media-days) cites kickoff times and team success as possible factors that influence attendance. 

As of 2018, it was the "seventh time in the last eight years that attendance has declined" [FunBuzz](https://fanbuzz.com/college-football/cfb-attendance-2019/). Clearly, the phenomenon of declining attendance is evident but there does not appear to be a clear and agreed upon cause. This made me want to investigate and see if I could uncover any trends over the past 7 seasons. While the dataset I will be using does not include pricing information, technology use or seat type data, it will allow me to uncover how stadium capacity, matchup quality and weather factor into attendance. It is most likely that many factors are simultaneously contributing to the decline of attendance. 

Since I knew this was a problem that has been identified, I was really interested in doing some numerical analysis to see if I could find any correlations with dropping attendance. I wanted to explore several varied aspects of this since many ideas have been tossed around in media outlets of what is causing this decline. Identifying factors that either do or do not appear to be tied to the number of people attending games will help build a more comprehensive understanding of what impacts NCAA football attendance and thus help schools reverse this trend.


## 6. Methodology

*Note: attendance percentage = game attendance / stadium capacity (this is allow for normalizing stadium size as it varies wildly)*

**H1:**
I will join the game info with the venue data and calculate average proportions of attendance per stadium capacity. I will then make two tables, one with the 5 largest stadiums and one with the 5 smallest stadiums in terms of raw capacity. I will then be able to compare and see if the smaller stadiums seem to have larger or smaller average attendance ratios. The output will be 2 tables.

**H2:**
I will join the game data with the rankings data and make 2 boxplots: one with average attendance percentage for games when the home team is ranked (in the AP Top 25) and another for when the home team is unranked. I can compliment this with a t-test to determine if there is a statistical difference between these 2 populations like I hypothesize there is. 

**H3:**
I will join the game data with the rankings data and make 2 boxplots: one with average attendance percentage for games when the away team is ranked (in the AP Top 25)  and another for when the away team is unranked. I can compliment this with a t-test to determine if there is a statistical difference between these 2 populations like I hypothesize there is. 

**H4:**
I will create an indicator for conference vs non-conference games. The game data has the conference of the home and away team listed and if these match it is a conference matchup. I can then create 2 boxplots, one for attendance percentage for conference games and another for non-conference matchups. I can also conduct a t-test to determine if the attendance percentages differ between the two groups. This will allow me to conclude whether attendance is impacted by the conference aspect of the games as I hypothesize that it is. 

**H5:**
I will use a scatter plot to visualize attendance percentages vs kickoff temperatures. This will allow me to see if there is a relationship between gameday temperature and attendance. A scatter plot will allow any relationship to be visible, whether or not it is linear. 

**H6:**
I will generate a rain indicator column from the weather API response, with a 1 marking games with measured rainfall and 0 for those without. I will create 2 boxplots: one with the average attendance percentage during games where there was measured rainfall and another for games without rain. I will also conduct a t-test to see if there is a statistically significant difference between the attendance percentages of these two populations.
