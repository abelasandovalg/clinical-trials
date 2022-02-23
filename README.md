# National Institutes of Health (NIH) Clinical Trials Analysis 

## Project Motivation 
The cost of healthcare in the United States (US) is rising each and every day, especially within the prescription drug market. Big Pharma strategically uses the patent system to extend existing patents beyond their initial 20-year protection which in return, hurts drug innovation. To further investigate, this analysis compares the top ten drug companies to others within the clinical trials dataset across certain features. 

## Code
Languages: Python, SQL <br>
Packages: apache_beam, airflow

## Data 
This analysis contains data from two sources: 

[National Institutes of Health](https://clinicaltrials.gov/api/gui/ref/download_all) <br>
The NIH dataset contains slightly over 700,000 records with 15 tables in total. The primary key for the dataset is the nct_number. Additionally, notable tables include clinical studies main, clinical results, and interventions. 

[Harvard](https://www.aerodatalab.org/birds-eye-view-of-research-landscape) <br>
The Harvard Bird's Eye dataset contains aroudn 13,000 records with nct_number as the primary key field. This datset contains the data on all clinical trial registration records from ten large pharmaceutical companies. 

### Data Cleaning 
Data cleaning for the datset includes: 
- removing unnecessary tables
- removing unnecessary columns 
- casting TIMESTAMP to DATE data types 
- removing duplicates 

## Results 
Based on the top ten conditions, only two conditions were oversaturated by the top ten pharmaceutical companies: Diabetes Mellitus (Type 2) and Hypertension. Rheumatoid Arthritis clinical studies were split evenly among all pharmaceutical companies and the rest of the conditions were mostly conducted by other companies. 

## Future Improvements 
1. 'Conditions' is notable feature within the NIH Clinical Trials dataset. However, due to the large amount of conditions, this feature was not included in the analysis. In the future, grouping together similar conditions will allow for the inclusion of this feature in the analysis and visualization. 
2. The top ten pharmaceutical companies were based upon the Harvard Bird's Eye dataset. In the future, including additional 'Big Pharma' companies could allow for greater insights.
