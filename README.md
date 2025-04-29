# 311-calls-ny

This data exploration goes into complaint patterns of 311 calls across New York City boroughs using 2 datasets (311 service request data and the Census) in April 2025. We uncover trends in across different socioeconomic levels, racial groups, and neighborhoods amongst boroughs. We also look to see if any neighborhoods had a surge of specific complaints or if they were under-reporting compared to other neighborhood of similar population sizes. After cleaning the data, we use K-means clustering, isolation forests for anomalies to find similarities and differences in the data. Our insights provide practical and actionable steps for a possible intervention. 

## How to Navigate

download_data.ipynb - Grabbing 311 report data from the API using Socrata. Perform data preprocessing (calls without zip code, zip codes have >0 population, etc). Repeated for the Census API data. Merge the data based on zip code. 

data_exploration.ipynb - From there, we rank complaint types and their respective frequency. Also analyze complaints via racial demographics and report variability. 

ML_models.iypnb - Perform an analysis using isolation forests to identify outliers in reporting tendencies of certain neighborhoods, specifically tied to the socioeconomic status of that zip code. Feature engineering analysis (such as surge factor and change rate, amongst other variables) were performed here. Z-scores and K-means clustering were also computed and implications were identified. 

## How to obtain the data used

### 311 Service Requests from 2010 to Present 

The 311 Service Requests from 2010 to Present dataset contains 39.8 million rows and 41 columns. Of the 39.8 million rows, we will be working with the most recent 100000 rows, from 2025-04-11 17:37:44 to 2025-04-23 01:51:16, due to the size of the data. The size and scale of 311 reports in every zip code confirms the existence of the problems. Columns include the unique key for the call that was made, the data the request was created and closed, which agency the 311 call should be directed to, the complaint type, the location of the incident, etc. 

The data was pulled from an API source.
https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9/about_data 
### United States Census Bureau, American Community Survey, 2020

The American Community Survey (ACS) is an ongoing survey that provides data every year—giving communities the current information they need to make important decisions. The ACS covers a broad range of topics about social, economic, housing, and demographic characteristics of the U.S. population.
Data, using a census API key, can be found here:
https://www.census.gov/programs-surveys/acs/data.html
https://data.census.gov/