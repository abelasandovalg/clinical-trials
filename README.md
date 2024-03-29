# National Institutes of Health (NIH) Clinical Trials Analysis 

## Project Motivation 
The cost of healthcare in the United States (US) is rising each and every day, especially within the prescription drug market. Big Pharma strategically uses the patent system to extend existing patents beyond their initial 20-year protection which in return, hurts drug innovation. To further investigate, this analysis compares the top ten drug companies to others within the clinical trials dataset across certain features. 

## Code
**Languages**: Python, SQL <br>
**Packages**: apache_beam, airflow

## Data 
This analysis contains data from two sources: 

[**National Institutes of Health**](https://clinicaltrials.gov/api/gui/ref/download_all) <br>
The NIH dataset contains slightly over 700,000 records with 15 tables in total. The primary key for the dataset is the nct_number. Additionally, notable tables include clinical studies main, clinical results, and interventions. 

[**Bird's Eye**](https://www.aerodatalab.org/birds-eye-view-of-research-landscape) <br>
The Bird's Eye dataset contains aroudn 13,000 records with nct_number as the primary key field. This datset contains the data on all clinical trial registration records from ten large pharmaceutical companies. 

### Data Cleaning 
Data cleaning for the datset includes: 
- removing unnecessary tables
- removing unnecessary columns 
- casting TIMESTAMP to DATE data types 
- removing duplicates 

## File Descriptions
`*_beam.py`: Python files used to create modeled tables using BigQuery <br>
`*_beam_dataflow.py`: Python files used to create final modeled tables using BigQuery <br>
`erd-*.pdf`: Entity relationship diagrams (ERD) <br>
`*_ingest.ipynb`: Notebooks used to explore initial datasets  <br>
`*_modeled.ipynb`: Notebooks used to create modeleted tables from initial staging <br>
`nih_joins.ipynb`: Notebook used to explore cross-dataset queries using joins <br>
`nih_erd_staging_queries.ipynb`: Notebook used to create and modify tables and detect duplicates for final ERD staging <br>
`nih_analysis.ipynb`: Initial data analysis for NIH dataset <br>
`cross_dataset_analysis.ipynb`: Cross-dataset analysis + view creation for final dashboard <br>
`nih_workflow.py`: Google Airflow workflow/pipeline setup using DAGs and *_beam_dataflow.py files <br>
`slides.pdf`: Final presentation slides <br>

## Results 
In terms of clinical trial status, the top ten pharmaceutical companies had slightly more completed clinical trials. However, among the other categories, all pharmaceutical companies had similar percentage amounts. 

![overall_status](https://github.com/abelasandovalg/clinical-trials/blob/main/images/overall_status.png)

Based on the top ten conditions, only two conditions were oversaturated by the top ten pharmaceutical companies: Diabetes Mellitus (Type 2) and Hypertension. Rheumatoid Arthritis clinical studies were split evenly among all pharmaceutical companies and the rest of the conditions were mostly conducted by other companies. 

![conditions](https://github.com/abelasandovalg/clinical-trials/blob/main/images/conditions.png)

## Future Improvements 
1. 'Conditions' is notable feature within the NIH Clinical Trials dataset. However, due to the large amount of conditions, there are certain conditions that overlap with one another. In the future, grouping together similar conditions will allow for a more accurate analysis and visualization. 
2. The top ten pharmaceutical companies were based upon the Harvard Bird's Eye dataset. In the future, including additional 'Big Pharma' companies could allow for greater insights.
