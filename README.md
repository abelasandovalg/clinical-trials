# National Institutes of Health (NIH) Clinical Trials Analysis

## Project Motivation 
The cost of healthcare in the United States (US) is rising each and every day, especially within the prescription drug market. Big Pharma strategically uses the patent system to extend existing patents beyond their initial 20-year protection which in return, hurts drug innovation. To further investigate, this analysis compares the top ten drug companies to others within the clinical trials dataset. 

## Code
Languages: Python, SQL <br>
Packages: apache_beam, airflow

## Data 
This analysis contains data from two sources: 

[National Institutes of Health](https://clinicaltrials.gov/api/gui/ref/download_all) <br>
The NIH dataset contains slightly over 700,000 records with 15 tables in total. The primary key for the dataset is the nct_number. Additionally, notable tables include clinical studies main, clinical results, and interventions. 

[Harvard](https://www.aerodatalab.org/birds-eye-view-of-research-landscape) <br>
The Harvard Bird's Eye dataset contains aroudn 13,000 records with nct_number as the primary key field. This datset contains the data on all clinical trial registration records from ten large pharmaceutical companies. 

## Results 


## Future Improvements 
'Conditions' is notable feature within the NIH Clinical Trials dataset. However, due to the large amount of conditions, this feature was not used in the analysis. In the future, grouping together similar conditions will allow for the inclusion of conditions in the analysis and visualization. 
