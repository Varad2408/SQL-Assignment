# SQL-Assignment

Q1: Find the top 5 counties with the highest total number of hospital beds.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.hospital_beds`
ORDER BY total_hospital_beds DESC
LIMIT 5;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/a0cabffe-5c2a-4bd3-b3af-1d39c38f2757)
Q2: Retrieve the counties where the number of respiratory therapists (full-time and part-time) is null in the staffing table.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.staffing`
WHERE respiratory_therapists_ft IS NULL AND respiratory_therapists_pt IS NULL;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/4d1828ec-f7fa-41a8-b54c-cc4fe38e1620)
Q3: Find the counties where the percentage of burn care beds to total hospital beds is between 5% and 100%  
```sql


Q4: Find the counties with a cardiac intensive care FTE greater than 10 in the staffing table.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.staffing`
WHERE cardiac_intensive_care_fte > 10;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/60424285-4645-4741-b3a9-854ed3b9dc72)
Q5: Find the average total nursing home personnel (full-time and part-time) per county.
```sql
SELECT county_name, AVG(total_nursing_home_personnel_pt + total_nursing_home_personnel_ft) AS avg_personnel
FROM `bigquery-public-data.covid19_aha.staffing`
GROUP BY county_name;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/46f578f8-34f9-48c0-8d17-248c57029769)




