## 2. Vehicle Model Research - Truck
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
<img width="203" alt="image" src="https://github.com/user-attachments/assets/99228919-ab70-43f1-bb0b-fa3c1c0bdd5a">

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
<img width="403" alt="image" src="https://github.com/user-attachments/assets/48d1adbe-1dd4-4967-aa3b-f7dd13c885cc">

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
<img width="325" alt="image" src="https://github.com/user-attachments/assets/833e0eb0-75ab-4dbc-aef7-dd578adbaa75">

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
<img width="396" alt="image" src="https://github.com/user-attachments/assets/dd5a8a8b-9c26-4288-9144-8a687676fe99">
<img width="402" alt="image" src="https://github.com/user-attachments/assets/ee5e6214-a57b-4f89-ba69-a5bb36e9792b">
<img width="402" alt="image" src="https://github.com/user-attachments/assets/007a67c1-15b2-4287-82e4-8e81e9da4d94">

<img width="996" alt="image" src="https://github.com/user-attachments/assets/76db157c-7a94-44d6-bde2-2c70439c25ca">

-----
**Conclusion**

Out of the 2583 vehicles there are 202 options that are trucks.
Chevrolet and GMC offer the most truck options.
The year 2022 offers the most truck options.
For the individual years, Chevrolet offers the most in 2022, Ram offers the most in 2023, and GMC in 2024.
