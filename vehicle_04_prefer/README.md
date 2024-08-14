## 4. Vehicle Preference Research
-----
Next we will continute to minimize the data to find the top results by now including the preferred list of specifications. 

-----
```
Preferred Specs:
  - engine cylinders 6 - 8
  - Regular gas
  - highway milage per gallon >= 16
```
-----
1. Which make (manufacturers/car brands) offers the most vehicle options?
2. Which year offers the most vehicle options?
3. Which make (manufacturers/car brands) of each year offers the most vehicle options?

-----
**1. Which make (manufacturers/car brands) offers the most vehicle options?**

```
SELECT
  make,
  COUNT(make) AS vehicle_count
  FROM my.project 
  WHERE
    (cylinders BETWEEN 6 and 8)
      AND (fuel_type = 'Regular')
        AND (hwy_mpg >= 16)
GROUP BY
  make
ORDER BY
  vehicle_count DESC
```
 <img width="401" alt="make_preferred_count" src="https://github.com/user-attachments/assets/36d0a1f6-db6b-4253-a904-603b044eb419">

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
<img width="319" alt="year_preferred_count" src="https://github.com/user-attachments/assets/9268620d-450c-4135-93be-df169f0cdf8e">

-----
**3. Which make (manufacturers/car brands) of each year offers the most vehicle options?**

```
SELECT
  make AS vehicle_make_2022, -- change year to 2023, then 2024
  COUNT(make) AS vehicle_count
  FROM my.project
  WHERE
    (cylinders BETWEEN 6 and 8)
      AND (fuel_type = 'Regular')
        AND (hwy_mpg >= 16)
        AND (year = 2022) -- change year to 2023, then 2024
GROUP BY
  make
ORDER BY
  vehicle_count DESC
```
<img width="400" alt="preferred_make_2022" src="https://github.com/user-attachments/assets/d9226456-4e97-44da-a31a-d2f4907c040a"><img width="404" alt="preferred_make_2023" src="https://github.com/user-attachments/assets/3dd2d4e5-99e0-4edc-abd8-546aca52cccf"><img width="404" alt="preferred_make_2024" src="https://github.com/user-attachments/assets/ce9dceb6-82f7-440e-9de0-7e5a6179867c">

-----
**Conclusion**

From the research done on preferences added to the vehicle options:
The make (manufacturers/car brands) that offers the most options is Ford.
The year that offers the most options is a tie between 2022 and 2024.
And the make (manufacturers/car brands) of the individual years was Ford for all three.
