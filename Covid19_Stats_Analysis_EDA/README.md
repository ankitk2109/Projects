# COVID-19 STAT ANALYSIS & VISUALISATION.

### Data Identification

I have used following end points of the API to fetch my data.

  * Endpoint 1: To fetch the latest stats for all countries. https://coronavirus-monitor.p.rapidapi.com/coronavirus/cases_by_country.php.

  * Endpoint 2: To fetch Covid-19 stats for specified date and country. https://coronavirus-monitor.p.rapidapi.com/coronavirus/history_by_country_and_date.php

  * Enpoint 1: Returns real time stats of each country affected by Covid-19.
  
  * Enpoint 2: Returns variation of stat of the specified country on a particular date specified.
  
  * Every record returned from the above API are characterised by the following number of features.
    * 'country_name': Country affected by virus.
    * 'cases': Total number of cases till now.
    * 'deaths': Total deaths till now.
    * 'region': Region of the country affected
    * 'total_recovered': Total people recovered from the disease.
    * 'new_deaths': New deaths on current date.
    * 'new_cases': New cases on current date.
    * 'serious_critical': Number of people which are critical
    * 'active_cases': Total active cases.
    * 'total_cases_per_1m_population': Ratio of number of people affected in 1 million population.
    
### Data Collection

* __Constraints:__ The Data is very dynamic and changes every day. So to keep a track of all the days is difficult as new countries also keep on adding. Hence only data for last seven is used for data collection and analysis.

* __API fetching requirements:__ To fetch data we need authentication i,e Key and host which is being provided in headers.

* __Storage:__ The data collected from the API is in json format. So the data is first loaded into dataframe and stored into a csv file. Since the data is quite big fetching it from API every time is a time taking process hence stored in a csv file. Later that csv file is read into dataframe for easier pre-proccessing and analysis.

### Data Pre-processing and Analysis:

* Null value checks

* Removal of unnecessary fields

* Extracting Numerical Data

* Data Insights: Below are few visualizations
  
  ![WhatsApp Image 2020-04-03 at 6 36 52 PM](https://user-images.githubusercontent.com/26432753/78450988-86ed2e80-767a-11ea-9439-176d2058cc05.jpeg)


![WhatsApp Image 2020-04-03 at 6 37 17 PM](https://user-images.githubusercontent.com/26432753/78450991-8b194c00-767a-11ea-9af9-9f8b38a61f1c.jpeg)


![WhatsApp Image 2020-04-03 at 6 37 36 PM](https://user-images.githubusercontent.com/26432753/78450995-940a1d80-767a-11ea-96d6-4a1ff6d1a5cd.jpeg)


![WhatsApp Image 2020-04-03 at 6 38 19 PM](https://user-images.githubusercontent.com/26432753/78450997-979da480-767a-11ea-9f76-3feddb5cd319.jpeg)


![WhatsApp Image 2020-04-03 at 6 38 45 PM](https://user-images.githubusercontent.com/26432753/78451000-9b312b80-767a-11ea-9d48-6124ec1bba18.jpeg)


![WhatsApp Image 2020-04-03 at 6 36 37 PM](https://user-images.githubusercontent.com/26432753/78451003-9d938580-767a-11ea-9936-4076178faec2.jpeg)

