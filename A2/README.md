# [Assignment 2: Bias in Data](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A2:_Bias_in_data)

Data 512
Tara Wilson
October 5, 2019

## Goal

The goal of this assignment is to investigate bias in written text. To do so, several Wikipedia articles on political figures from various countries will be combined with population data and examined. The analysis contained in this repository looks into countries with the most/least coverage of politicians compared to their population, the countries with the highest/lowest proportion of quality articles about their politicians, and rankings of regions with article count per population and proportion of high quality articles.

## Table of contents

* source_data/
    * page_data.csv
    * WPDS_2018_data.csv
* bias_in_data_error_log.log
* hcds-a2-bias-in-data.ipynb
* README.md

## Data sources

#### Wikipedia politicians by country dataset (page_data.csv)

This dataset is available [via Figshare](https://figshare.com/articles/Untitled_Item/5513449). The zip file can be downloaded and then the dataset used is `country\data\page_data.csv`. The citation for this data is:
Keyes, Os (2017): Politicians by Country from the English-language Wikipedia. figshare. Dataset.

#### Population dataset (WPDS_2018_data.csv)

This dataset is published by the Population Reference Bureau and is drawn from the [world population datasheet](https://www.prb.org/international/indicator/population/table/). The values used in this analysis are from 2018.

## Output files

#### ORES API Error log (bias_in_data_error_log.log)

This log file contains a list of `revision_id`'s for which I was unable to get a proper ORES score response.

#### Resulting dataset for analysis (wp_wpds_politicians_by_country.csv)

|   column name  |   description  |
|:--------------:|:--------------:|
|country         |Country name|
|article-name    |Name of political Wikipedia article|
|revision_id     |Revision ID of the article|
|article_quality |Predicted article quality class from ORES API|
|population      |Population of the country from WPDS, in Millions|

## Resources ??? Data processing?

