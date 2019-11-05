# A4: Final Project Proposal
### Data 512
### November 3, 2019
### Tara Wilson

## 1. Motivation/problem statement

As a huge college football fan, I wanted to do my project on a topic I care a lot about and in an area that I already have domain knowledge in. Specifically, I think it would be interesting to look at factors driving game attendance. Attendance is a huge part of revenue, but is also important for the program as it helps the school come across as well represented. I think some factors included in the dataset, such as venue capacity, success of team and challenge of opponent, all of which can be found in this same dataset, have significant impact on attendance. If I wanted to bring in additional data to create more of a challenge I think looking at gameday weather would produce interesting analysis as well.

I want to strengthen my data communication skills through this assignment – both in terms of reproducible code and in terms of analysis and visualizations. I think sports data poses an intriguing challenge since there is a specific set of vocabulary in the space that fans are used to so I will try to balance this while also making my project interpretable to the general public. I think this is an important aspect of human centered data science, as analysis that cannot be understood by the intended audience does not make for successful research. I want to strengthen my feature engineering skills as well so that I can practice generating fields such as indicators. I think the vast amounts of different type of information in this dataset will help me answer the questions I hope to, as well as provide an opportunity to improve my Python and reproducible research skills.


## 2. Data used

I plan to use the College Football database, aggregated by Bill Radjewski. The dataset contains information about most all aspects of college football including game data, drive data, play by play data, team data, player data, coach data, venue data and player/game statistics. This dataset has a good mix of categorical and quantitative data which will help give me good experience. 

The data is available [here](https://github.com/BlueSCar/cfb-database), and I will access it using [this API](https://api.collegefootballdata.com/api/docs/?url=/api-docs.json#/). The data is made available under a [standard MIT License](https://github.com/BlueSCar/cfb-database/blob/master/LICENSE).

This data is relevant to my problem statement because it covers most all aspects of college football. There should be ample information to answer the questions I choose, as well as room to explore additional factors if desired.

In terms of ethical concerns, the data does contain identifiable information on athletes such as height, weight, and hometown. However, I believe this is a side effect of playing NCAA football as this information can easily be found on team rosters, scouting websites, etc. so I do not believe there are any real privacy issues. 

## 3. Unknowns and dependencies

My biggest concern is the availability of the dataset since there are no guarantees about up-time, etc. To combat this, I am planning to store local copies of the data I will use for the analysis once I have completed the API calls. I checked a subset of the data and it looks correct and complete but another potential roadblock would be incomplete sections of the data that would be necessary for a total analysis causing me to have to pivot. Since the data is so vast and in an area I am curious about I also need to be cognizant of scope creep and ensure I stay answering my proposed questions only.
