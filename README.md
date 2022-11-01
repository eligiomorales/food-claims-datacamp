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
![](https://github.com/eligiomorales/food-claims-datacamp/blob/main/images/bar-chart.png)
