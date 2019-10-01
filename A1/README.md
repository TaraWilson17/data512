# [A1: Data Curation](https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A1:_Data_curation)

## Table of contents

* en-wikipedia_traffic_200712-201809.csv
* en-wikipedia_traffic_200712-201809.png
* hcds-a1-data-curation.ipynb
* LICENSE.md
* pagecounts_desktop-site_200801-201607.json
* pagecounts_mobile-site_200801-201607.json
* pageviews_desktop_201507-201908.json
* pageviews_mobile-app_201507-201908.json
* pageviews_mobile-web_201507-201908.json

----

## Data acquision

The data from this project was collected from the [Wikimedia REST API](https://www.mediawiki.org/wiki/REST_API).

Data from December 2007 - July 2016 was gathered from the [Legacy Pagecounts API](https://wikimedia.org/api/rest_v1/#/Legacy%20data).
The parameters used in the query were:
|----param----|----value(s)----|
|:-----------:|:--------------:|
|---project---|--en.wikipedia.org--|
|---access-site----|--desktop-site, mobile-site--|
|---granularity----|--monthly--|
|---start----|--2007120100--|
|---end----|--2016073100--|

Data from July 2015 - August 2019 was gathered from the [Pageviews API](https://wikimedia.org/api/rest_v1/#/Pageviews%20data).
The parameters used in the query were:
|----param----|----value(s)----|
|:-----------:|:--------------:|
|---project---|--en.wikipedia.org--|
|---access----|--desktop, mobile-site, mobile-app--|
|---agent----|--user--|
|---granularity----|--monthly--|
|---start----|--2015070100--|
|---end----|--2019083000--|
* The Pageviews API allows the agent query parameters which filters out spider views. This drives the lower counts returned from the new API.

----

## Data processing

1. Data from the Pageviews API was aggregated at the mobile level by summing accross each month the counts of pageviews for the `mobile-app` and `mobile-web` query results

2. Timestamps were broken out into the year and month, removing the date and hour data 

3. All query results were combined to one table

4. For months where the query type returned no results, 0's replaced the nan markers

5. `pagecount_mobile_views` and `pagecount_desktop_views` were summed to create an additional column for `pagecount_all_views` 

6. `pageview_mobile_views` and `pageview_desktop_views` were summed to create an additional column for `pageview_all_views` 

7. A .csv file was generated with the following data:

|----Column Name----|---Data Format---|
|:-----------------:|:---------------:|
|--------year-------|------YYYY-------|
|-------month-------|--------MM-------|
|----pagecount_all_views----|----`pagecount_mobile_views` + `pagecount_desktop_views`----|
|----pagecount_desktop_views----|----# of desktop views per month----|
|----pagecount_mobile_views----|----# of mobile views per month----|
|----pageview_all_views----|----`pageview_mobile_views` + `pageview_desktop_views`----|
|----pageview_desktop_views----|----# of desktop views per month----|
|----pageview_mobile_views----|----`pageview_mobile-app` + `pageview_mobile_web`----|

----

## Analysis


data and code descriptions, attributions and
provenance information, and hyperlinks to all relevant resources and documentation
(inside and outside the repo)

information to reproduce the analysis, including data descriptions, attributions and provenance information, and descriptions of all relevant resources and documentation (inside and outside the repo) and hyperlinks to those resources.