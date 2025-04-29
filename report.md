# Identifying Potential Civic Underreporting in NYC: A Machine Learning Approach Using 311 and Census Data


### Author:
- [Eunice Figueroa] <ef2719@barnard.edu>
- [Kevin Gutierrez] <kmg2226@columbia.edu>


## Problem
Civic engagement is critical to ensuring that community needs are met through public services. In New York City, 311 service requests allow residents to report non-emergency issues, enabling local agencies to respond and allocate resources. However, disparities in 311 usage may reflect underlying inequities: neighborhoods with significant local issues might underreport due to barriers like lack of trust, technological access, language gaps, or general awareness.
This project investigates whether certain NYC neighborhoods are at risk of civic underreporting — that is, experiencing local issues but making fewer 311 complaints than expected. By combining 311 service request data with Census demographic and socioeconomic data, we aim to identify zip codes where civic engagement through 311 reporting appears unusually low, using machine learning-based anomaly detection techniques.


## Audience and Value 
Our primary audience includes city government agencies, urban planners, and community advocacy organizations focused on equitable service delivery. 

The value of this project lies in its ability to flag communities that may be underserved not because of a lack of need, but due to barriers in civic reporting. Identifying these neighborhoods can help policymakers, prioritize outreach and education initiatives, improve accessibility of reporting systems (e.g., multilingual services), and allocate resources more equitably based on need rather than only reported incidents.

By revealing hidden civic engagement gaps, the project supports efforts to strengthen community trust, representation, and responsiveness in public services.

## Abstract
After curating and merging the datasets, we engineered features such as the number of complaints per 10,000 residents to normalize complaint activity across zip codes. Exploratory data analysis revealed that complaint rates were generally stable in areas with lower poverty rates but showed signs of underreporting in neighborhoods where poverty exceeded 40%. Racial breakdowns indicated variability in complaint behavior, with Black-majority zip codes showing slightly higher complaint rates but with substantial variability, while Hispanic-majority communities appeared to have lower civic reporting activity. Some major racial groups, such as Asian communities, were not represented due to data limitations.

For machine learning modeling, we applied an Isolation Forest unsupervised anomaly detection algorithm to identify zip codes that displayed unusually low complaint activity relative to their demographics. Zip codes such as 10474 and 10454 in the Bronx and 11211 in Brooklyn were flagged as "Potential Underreporters," showing high poverty rates and low civic complaint rates. Wealthy, low-poverty zip codes with low complaints, such as 10282 in Manhattan, were also flagged, though they were interpreted with caution given different contextual expectations. Invalid median income values inherited during merging (e.g., -666,666,666) were treated as missing values to prevent distortion.

To strengthen the analysis, we engineered weekly complaint-based features such as change rate, surge factor, complaint diversity, and average resolution time. Descriptive statistics suggested that sudden changes in complaint rates and low diversity of complaint types could indicate localized issues or civic engagement barriers. We further standardized features and visualized z-scores, identifying right-skewed distributions in poverty measures and demographic concentrations, reinforcing the presence of systemic disparities in underreporting potential.

Finally, we applied K-Means clustering with Principal Component Analysis (PCA) visualization to group boroughs based on their complaint type profiles. Three clusters emerged: Staten Island was isolated with a focus on outdoor and environmental issues; the Bronx exhibited concerns around smoking, water quality, and noise; while Brooklyn, Queens, and Manhattan showed a more balanced distribution of complaints. These cluster findings provide guidance for borough-specific outreach strategies.

Overall, our approach combined exploratory data analysis, feature engineering, unsupervised anomaly detection, and unsupervised clustering to uncover potential civic underreporting across NYC. Our findings suggest that targeted outreach—especially in low-income neighborhoods with low complaint activity—could help improve civic engagement and ensure more equitable service delivery. The project demonstrates how applied machine learning can support data-driven urban planning and resource allocation decisions.