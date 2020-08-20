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

* #### Dates

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Date (bins) | date | Aggregated cases dates grouped by weekly bins | JHU CSSE |
| Dates Reformatted | date | Aggregated cases dates with format changed from English to Spanish | JHU CSSE |
| Max Date | date | Calculated measure to create the week over week animation in the scatter plot | JHU CSSE |


* #### Cases

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Argentina | integer | Aggregated cases in Argentina | JHU CSSE |
| Brazil | integer | Aggregated cases in Brazil | JHU CSSE |
| Chile | integer | Aggregated cases in Chile | JHU CSSE |
| Date | date | Date of aggregated cases | JHU CSSE |
| Dates Reformatted | date | Dates of aggregated cases with format changed from English to Spanish | JHU CSSE |
| Index | integer | Table Index | - |
| NewCasesUY | integer | Calculated column with the new daily cases in Uruguay | - |
| Original Date | date | Original date of aggregated cases | JHU CSSE |
| Paraguay | integer | Aggregated cases in Paraguay | JHU CSSE |
| PrevObjUY | integer | Calculated column with the aggregated cases value from the previous date for Uruguay | - |
| Uruguay | integer | Aggregated cases in Uruguay | JHU CSSE |
| CasesPopAR | integer | Calculated measure of total cases per 10.000 population in Argentina | - |
| CasesPopBR | integer | Calculated measure of total cases per 10.000 population in Brazil | - |
| CasesPopCH | integer | Calculated measure of total cases per 10.000 population in Chile | - |
| CasesPopPY | integer | Calculated measure of total cases per 10.000 population in Paraguay | - |
| CasesPopUY | integer | Calculated measure of total cases per 10.000 population in Uruguay | - |


* #### Deaths

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Argentina | integer | Aggregated deaths in Argentina | JHU CSSE |
| Brazil | integer | Aggregated deaths in Brazil | JHU CSSE |
| Chile | integer | Aggregated deaths in Chile | JHU CSSE |
| Dates Reformatted | date | Dates of aggregated deaths with format changed from English to Spanish | JHU CSSE |
| DeathsUY | integer | Calculated column with the new daily deaths in Uruguay | - |
| Index | integer | Table Index | - |
| Paraguay | integer | Aggregated deaths in Paraguay | JHU CSSE |
| PrevObjAR | integer | Calculated column with the aggregated deaths value from the previous date for Argentina | - |
| PrevObjBR | integer | Calculated column with the aggregated deaths value from the previous date for Brazil  | - |
| PrevObjCH | integer | Calculated column with the aggregated deaths value from the previous date for Chile  | - |
| PrevObjPY | integer | Calculated column with the aggregated deaths value from the previous date for Paraguay  | - |
| PrevObjUY | integer | Calculated column with the aggregated deaths value from the previous date for Uruguay  | - |
| Uruguay | integer | Aggregated deaths in Uruguay | JHU CSSE |
| DeatsPopAR | integer | Calculated measure of total deaths per 10.000 population in Argentina | - |
| DeatsPopBR | integer | Calculated measure of total deaths per 10.000 population in Brazil | - |
| DeatsPopCH | integer | Calculated measure of total deaths per 10.000 population in Chile | - |
| DeatsPopPY | integer | Calculated measure of total deaths per 10.000 population in Paraguay | - |
| DeatsPopUY | integer | Calculated measure of total deaths per 10.000 population in Uruguay | - |



* #### Recovered

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Dates Reformatted | date | Dates of aggregated recovered with format changed from English to Spanish | JHU CSSE |
| Index | integer | Table Index | - |
| Original Date | date | Original date of aggregated recovered | JHU CSSE |
| PrevObjRecUY | integer | Calculated column with the aggregated recovered value from the previous date for Uruguay  | - |
| RecoveredUY | integer | Calculated column with the new daily recovered in Uruguay | - |
| Uruguay | integer | Aggregated recovered in Uruguay | JHU CSSE |


* #### Tests

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Country | string | Country | OWID |
| Date | date | Dates of total tests | OWID |
| Population | integer | Total population of the country | **WHO** |
| Tests | integer |  Total tests in the country | OWID |
| Tests (per 10 000 population) | integer |  Calculated column with the total tests per 10.000 population in the country | - |


* #### Health Force and Population

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Country | string | Country | WHO |
| Hospital Beds (per 10.000 population) | integer | Total hospital beds per 10.000 population in the country | WHO |
| Medical Doctors (per 10.000 population) | integer | Total medical doctors per 10.000 population in the country | WHO |
| Nurses (per 10.000 population) | integer | Total nurses per 10.000 population in the country | WHO |
| Population | integer | Total population of the country | WHO |



* #### Cases and Deaths

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Cases | integer | Aggregated cases | JHU CSSE |
| Country | string | Country | JHU CSSE |
| Dates Reformatted | date | Aggregated cases and deaths dates with format changed from English to Spanish | JHU CSSE |
| Deaths | integer | Aggregated deaths | JHU CSSE |
| Index | integer | Table Index | - |



* #### Calcs

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| DeathRateUY | decimal | Calculated measure with the rate of total deaths per total cases in Uruguay | - |
| RecoveredRateUY | decimal | Calculated measure with the rate of total recovered per total cases in Uruguay | - |
| Refresh Date | date | Latest date of data refresh | - |

