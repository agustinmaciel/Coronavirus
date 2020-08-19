# Analysis of Coronavirus in Uruguay
![](/Images/Coronavirus_Logo.jpg)

The aim of this project is to showcase the current and historical trend in Coronavirus infections in Uruguay, and compare them to the regional trends.

The project is already live and automatically updating information on a daily basis and can be seen here: 
[Coronavirus in Uruguay](https://bit.ly/3a6ggZT)


## Table of Contents

## 1. Files Description

1. `Coronavirus in Uruguay.pbix:` The latest Power BI file with all the data visualizations.
2. `RegionalHealthForce.xlsx:` The Excel file with the static data (nurses, medics and hospital beds).
3. `Images Folder:` All the images used in the readme.


## 2. Technologies Used:

* Power BI Desktop (creation of data model and visualizations)
* Power BI Service (daily data refresh and publish to web)
* GitHub (data files storage)
* Excel (data sources)


## 3. Data Sources:

1. For daily cases, daily deaths and daily recovered patients data:
[COVID-19 Data Repository by the Center for Systems Science and Engineering (CSSE) at Johns Hopkins University](https://github.com/CSSEGISandData/COVID-19).

2. For nurses, medics and hospital beds data:
[WHO Global Health Observatory data repository](https://apps.who.int/gho/data/node.home).

3. For daily tests data:
[Our World in Data repository](https://github.com/owid/covid-19-data/tree/master/public/data).


## 4. Data Model:
![](/Images/DataModel.PNG)


### Tables and fields

#### Dates

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Date (bins) | date | Dates grouped by weekly bins | JHU CSSE |
| Dates Reformatted | date | Dates with format changed from English to Spanish | JHU CSSE |
| Max Date | date | Calculated field to display the latest data update | JHU CSSE |


#### Cases and Deaths

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Cases | integer |Total cases grouped by country | JHU CSSE |
| Country | string | Country | JHU CSSE |
| Dates Reformatted | date | Dates with format changed from English to Spanish | JHU CSSE |
| Deaths | integer | Total deaths grouped by country | JHU CSSE |
| Index | integer | Table Index | Power BI |


#### Health Force and Population

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Country | string | Country | WHO |
| Hospital Beds (per 10 000 population) | integer | Number of hospital beds per 10 000 population in the country | WHO |
| Medical Doctors (per 10 000 population) | integer |  Number of medical doctors per 10 000 population in the country | WHO |
| Nurses (per 10 000 population) | integer |  Number of nurses per 10 000 population in the country | WHO |
| Population | integer | Total population of the country | WHO |


#### Tests

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Country | string | Country | OWID |
| Date | date | Date | OWID |
| Population | integer | Total population of the country | OWID |
| Tests | integer |  Total tests in the country | OWID |
| Tests (per 10 000 population) | integer |  Number of tests per 10 000 population in the country | OWID |



