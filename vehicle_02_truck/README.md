## Vehicle Truck Research
### First Requirement - Size Class
-----
The first and main requirement that was listed was that the size class of the vehicle was to be a truck.
Here we will use SQL to help organize the dataset and observe which make (manufacturers/car brands) and which year (2022 - 2024) will most likely be our future vehicle based on size class requirement.

-----
1. How many of the 2583 vechiles are listed as trucks?
2. Which make (manufacturers/car brands) offers the most truck options?
3. Which year offers the most truck options?
4. Which  make (manufacturers/car brands) offers the most truck options yearly?
-----

**1. How many of the 2583 vehciles are listed as trucks?**
```
SELECT
  COUNT(size_class) AS truck_count
FROM my.project
WHERE
  size_class LIKE '%Truck%'
```
<img width="203" alt="vehicle_truck_count" src="https://github.com/user-attachments/assets/984f5c72-9170-4d37-a178-9087b37155d5">
-----

**2. Which make(manufacturers/car brands) offers the most truck options?**

Here I decided to save a datatable of the data where the vehicles are trucks

```
SELECT
  *
FROM my.project
WHERE
  size_class LIKE '%Truck%'
ORDER BY
  make
```

Then I queried for which make (manufacturers/car brands) offer the most truck options
```
SELECT
  make,
  COUNT(make) AS truck_models
FROM my.project
WHERE
  size_class LIKE '%Truck%'
GROUP BY
  make
ORDER BY
  truck_models DESC
```
<img width="403" alt="make_truck_count" src="https://github.com/user-attachments/assets/e4650f5e-ac12-4ab3-ab0f-bca0b769fcc4">
-----

**3. Which year offers the most truck options?**
```
SELECT
  year,
  COUNT(make) AS truck_models
FROM my.project
WHERE
  size_class LIKE '%Trucks%'
GROUP BY
  year
ORDER BY
  truck_models DESC
```
<img width="325" alt="year_truck_count" src="https://github.com/user-attachments/assets/61b0cbbe-b5a6-4525-8cc0-5817a55a4805">
-----

**4. Which make(manufacturers/car brands) offers the most truck options yearly?**
```
SELECT
  make AS vehicle_truck_2022 -- change year to 2023, then 2024
  COUNT(make) AS truck_models
FROM my.project
WHERE
  (size_class LIKE '%Truck%')
    AND (year = 2022 -- change year to 2023, then 2024
GROUP BY
  make
ORDER BY
  truck_models DESC
```
<img width="396" alt="truck_count_2022" src="https://github.com/user-attachments/assets/a8ec732b-602f-4ddf-a253-f853c0d4cf6d"><img width="402" alt="truck_count_2023" src="https://github.com/user-attachments/assets/89b58ab8-36ad-4456-be7c-7330e9c99320"><img width="402" alt="truck_count_2024" src="https://github.com/user-attachments/assets/9da88009-1bb4-4e41-b908-ecb565e68b23">

<img width="996" alt="truck_model_year" src="https://github.com/user-attachments/assets/a7b9b0b9-71ec-4a6f-ba4c-1d40a9ad0a2f">


-----
**Conclusion**

Out of the 2583 vehicles there are 202 options that are trucks.
Chevrolet and GMC offer the most truck options.
The year 2022 offers the most truck options.
For the individual years, Chevrolet offers the most in 2022, Ram offers the most in 2023, and GMC in 2024.
