# ETL_Project_Repo

# Measles in 2019
#### By: Ankit Rana and Suvarna Sampale

#### ETL Project
In our project, we extracted, transformed, and loaded data related to measles in 2019.  Measles, a congtagious respiratory
virus can lead to complications, especially in babies and young children.  Its symptoms include cough, runny nose,
rash, and red, watery eyes.  There have been recent reports of measles outbreaks in the NY and NJ area.

We obtained our dataset from the CDC at the following website:
https://healthdata.gov/dataset/nndss-table-1v-malaria-measles-imported-0.
The data was provided in a csv file format and a json file format.
The data provides information on provisional cases of measles reported to the CDC from different
jurisdictions around the country in 2019 up until August of 2019.  The cases are called provisional because of the need
for case follow-up.  The CDC finalizes these following the end of the calendar year.  Some additional information that we
collected to help understand the information in our dataset is in Word document in our project folder called "Notes."
We also scraped data related to measles from the CDC website.

#### Extraction of Data

1. The CSV and JSON file were obtained from the CDC at this website: https://healthdata.gov/dataset/nndss-table-1v-malaria-measles-imported-0.

2. The html data was scraped from the following CDC website: https://www.cdc.gov/mmwr/volumes/68/wr/mm6817e1.htm


#### Transformation of Data

Steps to transform CSV and JSON data
1. Dropped all columns related to malaria since we were only focusing on measles
2. Selected the columns we were interested in querying and renamed them so they were easier to search.
3. We created tables with columns of related data.
4. In certain instances, we aggregated columns of data related to imported and indigeniousis measles cases to get a combined count.  Indigenious cases originated in the US and imported cases originated outside of the US, but both cases exist in the US.
5. In certain instances, we dropped NA values, because information as of the current week was not available or reported.

Steps to Transform Webscraped data.
1. Used BeautifulSoup to scrape https://www.cdc.gov/mmwr/volumes/68/wr/mm6817e1.htm for tables.
2. Once tables were found, they were loaded into a Pandas Dataframe.
3. Transformed the dataframe by creating multiple tables from the larger table

#### Load
We loaded the tables we selected into MongoDB using PyMongo
The reason why we chose MongoDB was because it was more faster and efficient and people would be able to pull data related to their specific reporting area and find out whether there was  recent outbreak quickly.
