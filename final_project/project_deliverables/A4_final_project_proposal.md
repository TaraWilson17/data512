# A4: Final Project Proposal
### Data 512
### November 3, 2019
### Tara Wilson

## 1. Motivation/problem statement

Why are you planning to do this analysis? 
Why is it potentially interesting and useful, from a scientific, practical, and/or human-centered perspective? 
What do you hope to learn? 
Note that you only need to describe your overall research goal at this stage; specific hypotheses or research questions aren’t necessary in the project proposal.

As a big college football fan, I wanted to do a project on a topic I have personal interest in. I think there's a vast array of possible questions to explore and a good mix of categorical and quantitative data. There are a lot of sports stastics so I think this poses an interesting constraint of understanding how end users expect the stastics be delivered so ??

## 2. Data used
What dataset do you plan to use, and why? 
Summarize what is represented in the dataset; 
Link to the dataset, and specify license/terms of use; 
Briefly justify why this dataset is relevant to your problem statement; 
Highlight any possible ethical considerations to using this dataset (and say why or why not).

I plan to use the College Football database, aggregated by Bill Radjewski. The dataset contains data from most all aspects of college football including game data, drive data, play by play data, team data, player data, coach data, venue data and player/game statistics. 

The data is available [here](https://github.com/BlueSCar/cfb-database), and I will access it using [this API](https://api.collegefootballdata.com/api/docs/?url=/api-docs.json#/). The data is made available under a [standard MIT License](https://github.com/BlueSCar/cfb-database/blob/master/LICENSE).

This data is relevant to my problem statement because it ??

The data does contain identifiable information on athletes such as height, weight, and hometown. However, I believe this is a side effective of playing NCAA football. My only other concern is where all of this data is aggregated from. 

## 3. Unknowns and dependencies

My biggest concern is the availability of the dataset since there are no guarentees about up-time, etc. To combat this, I am planning to store local copies of the data I will use for the analysis once I have completed the API calls. I checked a subset of the data and it looks correct and complete but a potential roadblock would be incomplete sections of the data that would be necessary for a complete analysis causing me to have to pivot. Since the data is so vast and in an area I am curious about I also need to be cognisant of scope creep and ensure I stay answering my proposed questions.
