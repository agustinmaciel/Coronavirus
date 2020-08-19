# Analysis of Coronavirus in Uruguay
![](/Images/Coronavirus_Logo.jpg)

The aim of this project is to showcase the current and historical trend in Coronavirus infections in Uruguay, and compare them to the regional trends.

The project is already live and automatically updating information on a daily basis and can be seen here: 
[Coronavirus in Uruguay](https://bit.ly/3a6ggZT)


## Table of Contents

## 1. Files Description

1. `Coronavirus in Uruguay.pbix:` The latest Power BI file with all the data visualizations.
2. `RegionalHealthForce.xlsx:` The Excel file with the static data (Nurses, Medics and Hospital Beds by Country).
3. `Images Folder:` All the images used here.


## 2. Technologies Used:

* Power BI Desktop (creation of data model and visualizations)
* Power BI Service (daily data refresh and publish to web)
* GitHub (data files storage)
* Excel (data sources)


## 3. Data Sources:

1. For daily cases, deaths and recovered patients data:
[Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE) repository](https://github.com/CSSEGISandData/COVID-19).

2. For Nurses, Medics and Hospital Beds data:
[WHO Global Health Observatory data repository](https://apps.who.int/gho/data/node.home).

3. For daily tests data:
[Our World in Data repository](https://github.com/owid/covid-19-data/tree/master/public/data).


## 4. Data Model:
![](/Images/DataModel.PNG)


### Tables and fields

#### Dates Table

| Field Name | Data Type | Description | Source |
| ----------- | ----------- | ----------- | ----------- |
| Date (bins) | date | Dates grouped by weekly bins | JHU CSSE |
| Dates Reformatted | date | Dates with format changed from English to Spanish | JHU CSSE |
| Max Date | date | Calculated field to display the latest data update | JHU CSSE |





