# SQL-Assignment

Q1: Find the top 5 counties with the highest total number of hospital beds.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.hospital_beds`
ORDER BY total_hospital_beds DESC
LIMIT 5;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/efca6e24-bcf2-44f5-94e2-48f67dfb1d63)
