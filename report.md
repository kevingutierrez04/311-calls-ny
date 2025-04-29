# Underreporting in NYC: STAT 3106 Applied Machine Learning

### Authors:
- [Eunice Figueroa] <ef2719@barnard.edu>
- [Kevin Gutierrez] <kmg2226@columbia.edu>


## Problem
Civic engagement is vital in any society to help improve the community’s way of life. In NYC, 311 calls are used to report anything from vehicles parked for too much time to noise pollution. As a result, the city can allocate resources to alleviate concerns. Using the 311 report data and the Census, we analyze any disparities in reporting from varying neighborhoods to identify trends. With the data, we identify zip codes that under report and find patterns in frequency of certain types of reports in the same neighborhood, prompting a targeted response. We primarily use anomaly detection ML techniques such as Isolation Forest.

## Audience and Value

Government agencies and local community groups can use this data to improve their services for a more equitable society.

Through our analysis, we hope to identify communities that need more assistance due to underreporting and not because of a lack of need, an important distinction.  Specifically, this could motivate officials to increase awareness for multilingual 311 services. Combating these issues will help improve community trust and representation in public services.

## Abstract

After cleaning the data and merging the datasets, we engineered features such as the number of complaints per 10,000 residents to normalize complaint activity across zip codes. Extreme outliers and otherwise faulty data were removed. Data analysis revealed that complaint rates showed signs of underreporting in neighborhoods where poverty exceeded 40%. Black-majority zip codes showed slightly higher complaint rates but with variability, while Hispanic-majority zip codes appeared to have lower civic reporting activity. A shortcoming of the analysis is that the data didn’t include the asian population.

We then implemented an Isolation Forest algorithm to identify zip codes that displayed unusually low complaint activity relative to their demographics. 10474 and 10454 in the Bronx and 11211 in Brooklyn were flagged as "Potential Underreporters," indicated by high poverty rates and low civic complaint rates. Interestingly, zip codes such as 10282 in Manhattan, were also flagged despite its economic stability.

To further pinpoint the analysis, we also computed weekly complaint-based features such as change rate, surge factor, complaint diversity, and average resolution time. Sudden changes in complaint rates and low diversity of complaint types could indicate issues that were prevalent to certain neighborhoods. We further standardized features and calculated z-scores, which resulted in right-skewed distributions in poverty measures and demographics. This supports the conclusion of systemic disparities present in reporting rates.

Finally, we used K-Means clustering and Principal Component Analysis (PCA) categorize boroughs based on the complaints they receive. Staten Island received with outdoor and environmental issues; the Bronx had mostly smoking, water quality, and noise complaints; while Brooklyn, Queens, and Manhattan were balanced in complaint distribution. Regardless, outreach in low-income zip codes with low complaint activity could help improve civic engagement and improve quality of life.