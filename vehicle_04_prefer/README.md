## 4. Vehicle Preference Research
-----
Next I will continue to minimize the data to find the top results by now including the preferred list of specifications

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
<img width="401" alt="image" src="https://github.com/user-attachments/assets/3c51713d-2919-422e-a074-5f3077277869">

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
<img width="319" alt="image" src="https://github.com/user-attachments/assets/a4383a9c-7bbe-4ab4-a31d-9f87d7d7771c">

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
<img width="400" alt="image" src="https://github.com/user-attachments/assets/b33edc0a-2246-4e5b-b64e-ac64f6f297c1">
<img width="404" alt="image" src="https://github.com/user-attachments/assets/c8bb8ec8-e25d-4e31-b32b-997b0f4dea2b">
<img width="404" alt="image" src="https://github.com/user-attachments/assets/2fbd47df-8795-4597-880f-779a4db73a26">

-----
**Conclusion**

From the research done on preferences added to the vehicle options:
The make (manufacturers/car brands) that offers the most options is Ford
The year that offers the most options is a tie between 2022 and 2024
And the make (manufacturers/car brands) of the individual years was Ford for all three
