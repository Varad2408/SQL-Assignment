# SQL-Assignment

Q1: Find the top 5 counties with the highest total number of hospital beds.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.hospital_beds`
ORDER BY total_hospital_beds DESC
LIMIT 5;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/efca6e24-bcf2-44f5-94e2-48f67dfb1d63)


Q2: Retrieve the counties where the number of respiratory therapists (full-time and part-time) is null in the staffing table.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.staffing`
WHERE respiratory_therapists_ft IS NULL AND respiratory_therapists_pt IS NULL;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/c0fafc26-510e-4f7e-b964-61560453c1a2)
