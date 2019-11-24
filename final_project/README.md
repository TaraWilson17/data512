# [Final project](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A7:_Final_project_report)

Data 512  
Tara Wilson  
Autumn 2019  

## Project goal

The goal of this assignment is to practice reproducible research and effectively communicate findings.
This research is about NCAA college football, specifically which factors influence attendance. 

## Project motivations



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
    * [A6_final_project_presentation.pdf](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A6:_Final_project_presentation)
* data_analysis.ipynb
* data_collection.ipynb
* LICENSE

### Data sources

### Analysis scripts

### Output files

#### Resulting dataset for analysis (seasons_2012-2018_attendance_data.csv)

|   column name        |   description  |
|:---------------------|----------------|
|attendance            |Count of attendees for game |
|away_conference       |Conference abbreviation for away team |
|away_line_scores      | |
|away_points           |Number of points scored by the away team during the game |
|away_team             |Name of away team |
|conference_game       |Boolean indicator of if home and away team are from the same conference |
|home_conference       |Conference abbreviation for home team |
|home_line_scores      | |
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
|max_temp              |Maximum temperature in the venue area on the day of the game |
|min_temp              |Minimum temperature in the venue area on the day of the game |
