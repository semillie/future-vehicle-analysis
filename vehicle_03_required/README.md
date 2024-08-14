## 3. Vehicle Requirement Research

Here we will sort the data based on all the requirements that were listed. 
I could do this based off of the truck datatable that I made, but thought it would be more fun to do a WHERE clause with multiple operators.

-----
```
Required Specs:
  - 2022 - 2024 year
  - truck
  - 4 Wheel Drive option
  - automatic transmission
```
-----
1. Which make (manufacturers/car brands) offers the most vehicle options?
2. Which year offers the most vehicle options?
3. Which make (manufacturers/car brands) of each year offers the most vehicle options?

-----

Here we will make a new datatable for only the vehicles that meet all the requirements
```
SELECT  
  *
FROM my.project 
WHERE
  (drivetrain LIKE '%4WD%'
    OR drivetrain LIKE '%4-Wheel Drive%')
  AND (transmission = 'Automatic')
  AND (size_class LIKE '%Truck%')
ORDER BY
  make
```
-----
**1. Which make (manufacturers/car brands) offers the most vehicle options?**

```
SELECT  
  make,
  COUNT(make) AS vehicle_count
FROM my.project 
GROUP BY
  make
ORDER BY
  vehicle_count DESC
```
<img width="408" alt="vehicle_required_make" src="https://github.com/user-attachments/assets/543a550f-0463-4942-942d-865ff65a6307">
<img width="499" alt="Screenshot 2024-08-08 at 9 19 33 PM" src="https://github.com/user-attachments/assets/86159dde-b175-45ea-b817-ac3f6d6b7fb3">

-----
**2. Which year offers the most vehicle options?**

```
SELECT  
  year,
  COUNT(make) AS vehicle_count
FROM my.project 
GROUP BY
  year
ORDER BY
  vehicle_count DESC
```
<img width="327" alt="vehicle_required_year" src="https://github.com/user-attachments/assets/e810c427-b788-4185-834b-fa31599d767a">

-----
**3. Which make (manufacturers/car brands) of each year offers the most vehicle options?**

```
SELECT  
  make AS vehicle_make_2022, -- change year to 2023, then 2024
  COUNT(make) AS vehicle_count
  FROM my.project 
WHERE
  year = 2022 -- change year to 2023, 2024
GROUP BY 
  make
ORDER BY
  vehicle_count DESC
```
<img width="413" alt="required_make_2022" src="https://github.com/user-attachments/assets/5a9f234f-a113-4467-8063-9fbed1a7f81b"><img width="408" alt="required_make_2023" src="https://github.com/user-attachments/assets/4b7ba34c-1fb9-441d-af1b-c88a2cf25865"><img width="407" alt="required_make_2024" src="https://github.com/user-attachments/assets/cbb5a2c6-28dc-4b57-925d-f7600b65b929">

-----
**Conclusion**

Chevrolet still holds the most options for a make (manufacturer/car brand).
Year 2024 has the most options of the years.
For the individual years, Chevrolet has the most options in 2022, GMC in 2023 and in 2024.
