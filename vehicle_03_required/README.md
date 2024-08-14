## 3. Vehicle Requirement Research

Here I sort the data based on all the requirements that were listed. 
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

Here I make a new datatable for only the vehicles that meet all the requirements
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
<img width="408" alt="image" src="https://github.com/user-attachments/assets/565e30b9-f1da-4d1f-8c67-846bf818042b">

<img width="499" alt="image" src="https://github.com/user-attachments/assets/52105dc6-9b93-4920-9d62-e5c0b479edf8">

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
<img width="327" alt="image" src="https://github.com/user-attachments/assets/a9225bb8-3394-4d7e-8bc7-fd4bccacbbcf">

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
<img width="413" alt="image" src="https://github.com/user-attachments/assets/b4f99b8e-75d2-4233-8b95-c3bfc598b468">
<img width="408" alt="image" src="https://github.com/user-attachments/assets/e690a61f-0bd9-4e6c-a8f5-04e69dbb9a8e">
<img width="407" alt="image" src="https://github.com/user-attachments/assets/1eeeb437-26fe-4d2b-9188-c4c26a401e4f">

-----
**Conclusion**

Chevrolet still holds the most options for a make (manufacturer/car brand).
Year 2024 has the most options of the years.
For the individual years, Chevrolet has the most options in 2022, GMC in 2023 and in 2024.
