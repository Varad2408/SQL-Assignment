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
Q3: Find the counties where the number of neonatal care FTE (full-time equivalent) is greater than 3.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.staffing`
WHERE neonatal_care_fte > 3;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/d91ac6d0-852a-4a63-a75f-e78fbbec1998)
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
Q.6 Find the counties where the total number of physicians and dentists (full-time and part-time) is greater than 50.
```sql
SELECT county_name
FROM `bigquery-public-data.covid19_aha.staffing`
WHERE physicians_and_dentists_ft + physicians_and_dentists_pt > 50;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/a793bf4c-561b-4f73-974f-6b5ee968b2fc)
Q.7 Find the counties where the number of psychiatric care beds is greater than the number of physical rehabilitation care beds.
```sql
SELECT h.county_name
FROM  `bigquery-public-data.covid19_aha.hospital_beds` h
WHERE h.psychiatric_care_beds > h.physical_rehabilitation_care_beds;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/8e02923c-af8d-40e1-a8e9-f5b21a8c70e3)
Q.8 Retrieve the counties with the highest total number of medical surgical intensive care beds.
```sql
SELECT county_name
FROM  `bigquery-public-data.covid19_aha.hospital_beds` h
ORDER BY medical_surgical_intensive_care_beds DESC
LIMIT 10;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/aeda8809-5c8e-4861-aeb4-1e33c53d6f27)
Q.9 Retrieve the counties with the lowest ratio of total hospital beds to total personnel (full-time and part-time).
```sql
SELECT h.county_name
FROM  `bigquery-public-data.covid19_aha.hospital_beds` h
JOIN `bigquery-public-data.covid19_aha.staffing` s ON h.county_fips_code = s.county_fips_code
ORDER BY h.total_hospital_beds / (s.total_personnel_pt + s.total_personnel_ft) ASC
LIMIT 14;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/4e2d4bfc-7ba1-4b30-a936-a7a7e46bdd53)

Q.10 Retrieve the counties where the ratio of registered nurses (full-time and part-time) to total hospital beds is highest.
```sql
SELECT h.county_name
FROM `bigquery-public-data.covid19_aha.hospital_beds` h
JOIN `bigquery-public-data.covid19_aha.staffing` s ON h.county_fips_code = s.county_fips_code
ORDER BY (s.registered_nurses_ft + s.registered_nurses_pt) / h.total_hospital_beds DESC
LIMIT 10;
```
![image](https://github.com/Varad2408/SQL-Assignment/assets/152723954/a282bc72-94da-4d91-a0a8-fcfead3cc867)







