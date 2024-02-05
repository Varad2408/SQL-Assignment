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

Q3: Find the counties where the percentage of burn care beds to total hospital beds is between 5% and 100%  
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.staffing`
WHERE respiratory_therapists_ft IS NULL AND respiratory_therapists_pt IS NULL;
SELECT h.county_name
FROM `bigquery-public-data.covid19_aha.hospital_beds` h
WHERE (h.burn_care_beds / h.total_hospital_beds) * 100 > 5;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/d81ac76e-9c03-4ad1-b8e3-0c4290b46fcd)
Q4: Find the counties with a cardiac intensive care FTE greater than 10 in the staffing table.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.staffing`
WHERE cardiac_intensive_care_fte > 10;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/60424285-4645-4741-b3a9-854ed3b9dc72)
Q5: Find the average total nursing home personnel (full-time and part-time) per county.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.staffing`
WHERE cardiac_intensive_care_fte > 10;
SELECT county_name, AVG(total_nursing_home_personnel_pt + total_nursing_home_personnel_ft) AS avg_personnel
FROM `bigquery-public-data.covid19_aha.staffing`
GROUP BY county_name;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/9fa6c92b-284d-454b-999c-52a1b1a01d12)



