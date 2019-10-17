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
* output_data/
    * wp_wpds_countries-no_match.csv
    * wp_wpds_politicians_by_country.csv
* bias_in_data_error_log.log
* hcds-a2-bias-in-data.ipynb
* LICENSE

### Data sources

#### Wikipedia politicians by country dataset (page_data.csv)

This dataset is available [via Figshare](https://figshare.com/articles/Untitled_Item/5513449). The zip file can be downloaded and then the dataset used is `country\data\page_data.csv`. The citation for this data is:
Keyes, Os (2017): Politicians by Country from the English-language Wikipedia. figshare. Dataset.

#### Population dataset (WPDS_2018_data.csv)

This dataset is published by the Population Reference Bureau and is drawn from the [world population datasheet](https://www.prb.org/international/indicator/population/table/). The values used in this analysis are from 2018.

### Output files

#### ORES API Error log (bias_in_data_error_log.log)

This log file contains a list of `revision_id`'s for which I was unable to get a proper Objective Revision Evaluation Service (ORES) score response.

#### Resulting dataset for analysis (wp_wpds_politicians_by_country.csv)

|   column name  |   description  |
|:--------------:|:--------------:|
|country         |Country name|
|article-name    |Name of political Wikipedia article|
|revision_id     |Revision ID of the article|
|article_quality |Predicted article quality class from ORES API|
|population      |Population of the country from WPDS, in Millions|

#### Resulting dataset without matches (wp_wpds_countries-no_match.csv)

This is the dataset resulting from the join of the 2 datasources with the ORES API responses where the datasets did not have data for all of the columns above. More detail in notebook file.

### Analysis files

#### Code notebook (hcds-a2-bias-in-data.ipynb)

Jupyter notebook with all code to bring in, clean, and analyze the data. Also includes a reflection on bias in the data.

## Data processing

1. Data is retrieved from respective sources above.
2. Data is cleaned, removing `Template` articles and aggregating by gepgraphic region.
3. ORES API calls are batches and made to retrieve predictions for all article revision IDs.
4. ORES results are merged with the page and population source data, with records without a match being saved to a seperate file.
5. Proportions of articles per population are generated for all countries and regions in the dataset.
6. Proportions of high-quality articles (FA or GA ORES predictions) per number of total articles are generated for all countries and regions in the dataset.
7. Result tables are generated.
8. Reflection on bias is completd in Notebook.

