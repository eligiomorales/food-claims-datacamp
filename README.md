# Data Analyst Associate Case Study
### Company: Viviendo - A claim analysis

Vivendo is a fast food chain in Brazil with over 200 outlets. As with many fast food establishments, customers make claims against the company. For example, they blame Vivendo for suspected food poisoning.

The legal team, who processes these claims, is currently split across four locations. The new head of the legal department wants to see if there are differences in the time it takes to close claims across the locations.

## Data Validation

Initially, I verified that the database, which consists of 98 rows and 8 columns, did not contain any duplicates. The next step was to verify null values in the 8 columns, of which I discovered 78 null values in the column 'cause'. To comply with the case study requirement, the null values in the "cause" field **were replaced with "unknown"**.

Upon examining the table's columns, I found that 'claim_id' contains "year" and sequential numbers for each year. **To enable further analysis**, two columns were added to the claims table, namely 'year' and 'claim_number'. These columns were populated by extracting the information from the 'claim_id' field. **This case study makes this assumption**.

For the 'location' field, it was verified that only the values "RECIFE", "SAO LUIS", "FORTALEZA", or "NATAL" are acceptable. The 'linked cases' field was also verified to only accept TRUE-FALSE values. Confirming that the **data is in compliance in both cases**.  However, while verifying that the 'cause' field accepts only "vegetable", "meat", or "unknown", there appears to be an error. Correcting **8 rows with typos**.

Next 'claim_amount' was the field to be parsed. The LC was extracted by removing the prefile '$R' and converting the type of the field **from varchar to numeric**. 

Finally, the 'time_to_close' field was analyzed, which, according to the given criteria, would consist of values starting at 1. The clean dataset is composed of **97 rows and 10 columns** after removing one row that had a negative value.

## Data Discovery and Visualization

#### Brief Report

- The number of claims varies between locations. With a difference of 12 claims, SAO LUIS and FORTALEZA had the worst and best performance, respectively. 
- There is also a difference in the average closing of claims between the locations. SAO LUIS and NATAL were the locations with the worst and best performance, respectively, with a 400-day difference approximately. 
- Even though the number of claims has increased in recent years, the average time required for claims to be closed has gradually decreased since 2015. 
- Although there is a significant difference in both the number of claims and the average closing time between locations, it is recommended that other variables, other than those included in the database, be considered. For example, level conformity with production processes per outlet, number of outlets and revenue per location.
- To reach these conclusions, only 87% of the total claims reported over the past five years were considered for analysis (see supporting criteria in the extended report).


#### Extended Report
As can be seen in the graph below, by taking advantage of the newly added 'year' field, we are able to understand how the data has changed over time. Therefore, it was possible to determine that, of all the claims in the database, **only 13% were generated in the first 6 years**. Further, this period is marked by the **highest number** of days for a claim to be closed.


![line bar](https://github.com/eligiomorales/food-claims-datacamp/blob/main/images/line-chart.png)


As a consequence of this particular characteristic of the data and the fact that there are variables not considered, such as an increase in sales, increase in number of outlets and improvements in the complaint management process, etc., it is understood that the analysis may be affected. Therefore, another assumption has been made, namely that only data **from 2016 to 2020 will be considered**.


Based on the number of claims across locations, SAO LUIS has the **highest number of claims** with 28 claims, as well as the **highest average resolution rate** (898.4 days).Hence, an in-depth analysis of the operations of this location would be necessary in order to identify the possible causes of the high number of days required to close claims. However, it is recommended that **other variables be considered as well**. Due to the fact that other variables may be relevant to analyze, for instance conformity with  production processes per outlet, number of outlets and revenue per location.  


![bar-charts](https://github.com/eligiomorales/food-claims-datacamp/blob/main/images/bar-chart.png)


By contrast, FORTALEZA and NATAL have the **lowest number** of claims and the lowest average closure rate (see graph below). In this regard, it appears that they can be considered as best practices for improving processes in the other two locations as well.


#### Disclaimers
- It is assumed that the field 'claim_id' consists of the year in which the complaint was filed and a number associated with that complaint. 
- For the analysis, only data from 2016 to 2020 were considered. 


