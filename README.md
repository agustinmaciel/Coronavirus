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
| Date (bins) | date | New daily cases dates grouped by weekly bins | JHU CSSE |
| Dates Reformatted | date | New daily cases dates with format changed from English to Spanish | JHU CSSE |
| Max Date | date | Calculated field to display the latest data update | JHU CSSE |


* #### Cases

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Argentina | integer | New daily cases in Argentina | JHU CSSE |
| Brazil | integer | New daily cases in Brazil | JHU CSSE |
| Chile | integer | New daily cases in Chile | JHU CSSE |
| Date | date | Date of new daily cases | JHU CSSE |
| Dates Reformatted | date | Dates with format changed from English to Spanish | JHU CSSE |
| Index | integer | Table Index | Power BI |
| NewCasesUY | integer | Total cases in Uruguay | JHU CSSE |
| Original Date | date | Original date of new daily cases | JHU CSSE |
| Paraguay | integer | New daily cases in Uruguay | JHU CSSE |
| PrevObjUY | integer | Calculated column with the value from the previous date for Uruguay | - |
| Uruguay | integer | New daily cases in Uruguay | JHU CSSE |
| CasesPopAR | integer | Calculated measure of cases by population in Argentina | - |
| CasesPopBR | integer | Calculated measure of cases by population in Brazil | - |
| CasesPopCH | integer | Calculated measure of cases by population in Chile | - |
| CasesPopPY | integer | Calculated measure of cases by population in Paraguay | - |
| CasesPopUY | integer | Calculated measure of cases by population in Uruguay | - |


* #### Deaths

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Argentina | integer | New daily deaths in Argentina | JHU CSSE |
| Brazil | integer | New daily deaths in Brazil | JHU CSSE |
| Chile | integer | New daily deaths in Chile | JHU CSSE |
| Dates Reformatted | date | Dates with format changed from English to Spanish | JHU CSSE |
| DeathsUY | integer | Total deaths in Uruguay | JHU CSSE |
| Index | integer | Table Index | Power BI |
| Paraguay | integer | New daily deaths in Paraguay | JHU CSSE |
| PrevObjAR | integer | Calculated column with the value from the previous date for Argentina | - |
| PrevObjBR | integer | Calculated column with the value from the previous date for Brazil  | - |
| PrevObjCH | integer | Calculated column with the value from the previous date for Chile  | - |
| PrevObjPY | integer | Calculated column with the value from the previous date for Paraguay  | - |
| PrevObjUY | integer | Calculated column with the value from the previous date for Uruguay  | - |
| Uruguay | integer | New daily deaths in Uruguay | JHU CSSE |
| DeatsPopAR | integer | Calculated measure of deaths by population in Argentina | - |
| DeatsPopBR | integer | Calculated measure of deaths by population in Brazil | - |
| DeatsPopCH | integer | Calculated measure of deaths by population in Chile | - |
| DeatsPopPY | integer | Calculated measure of deaths by population in Paraguay | - |
| DeatsPopUY | integer | Calculated measure of deaths by population in Uruguay | - |



* #### Recovered

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Dates Reformatted | date | Dates with format changed from English to Spanish | JHU CSSE |
| Index | integer | Table Index | Power BI |
| Original Date | date | Original date of new daily cases | JHU CSSE |
| PrevObjRecUY | integer | Calculated column with the value from the previous date for Uruguay  | - |
| RecoveredUY | integer | Total recovered in Uruguay | JHU CSSE |
| Uruguay | integer | New daily recovered in Uruguay | JHU CSSE |


* #### Tests

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Country | string | Country | OWID |
| Date | date | Date of new daily tests | OWID |
| Population | integer | Total population of the country | OWID |
| Tests | integer |  Total tests in the country | OWID |
| Tests (per 10 000 population) | integer |  Number of tests per 10 000 population in the country | OWID |


* #### Health Force and Population

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Country | string | Country | WHO |
| Hospital Beds (per 10 000 population) | integer | Number of hospital beds per 10 000 population in the country | WHO |
| Medical Doctors (per 10 000 population) | integer |  Number of medical doctors per 10 000 population in the country | WHO |
| Nurses (per 10 000 population) | integer |  Number of nurses per 10 000 population in the country | WHO |
| Population | integer | Total population of the country | WHO |



* #### Cases and Deaths

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Cases | integer |Total cases grouped by country | JHU CSSE |
| Country | string | Country | JHU CSSE |
| Dates Reformatted | date | New daily cases dates with format changed from English to Spanish | JHU CSSE |
| Deaths | integer | Total deaths grouped by country | JHU CSSE |
| Index | integer | Table Index | Power BI |



* #### Calcs

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| DeathRateUY | decimal | Calculated field with the rate of deaths in Uruguay | - |
| RecoveredRateUY | decimal | Calculated field with the rate of recovered in Uruguay | - |
| Refresh Date | date | Latest date of data refresh | - |

