## 5. Vehicle Add-On Feature Research

By minimizing the future vehicle list by requirements and preferences, there are 46 vehicles left that could be the future vehicle

To further determine the result, I acquired further data for add-on features
This dataset is the vehicle_features.csv.

-----
```
Add-On Feature Specs:
  - towing capacity >= 5500
  - apple-play
  - sunroof
  - keyless remote start
```
-----
1. How many vehicle options will there be after applying the add-on feature list?
2. Of that number of vehicle list, how many are from each year?
3. Which manufacturer has the most options for all years combined and each year individually?
-----

**1. How many vehicle options will there be after applying the add-on feature list?**
```
SELECT  
  COUNT(make) AS vehicle_count
FROM my.project
WHERE
  (apple_play = 'true')
    AND (sunroof = 'true')
      AND (keyless_start = 'true')
        AND (towing_cap >= 5500)
ORDER BY
  vehicle_count DESC
```
<img width="208" alt="image" src="https://github.com/user-attachments/assets/762023dc-976d-4fd3-af64-372c74be49cc">

-----
**2. Of that vehicle options, how many are from each year?** 
```
SELECT
  year,  
  COUNT(make) AS vehicle_count
FROM my.project
WHERE
  (apple_play = 'true')
    AND (sunroof = 'true')
      AND (keyless_start = 'true')
        AND (towing_cap >= 5500)
GROUP BY
  year
ORDER BY
  vehicle_count DESC
```
<img width="327" alt="image" src="https://github.com/user-attachments/assets/5ae697a3-9da7-4d49-a7e0-989c2e659772">

-----
**3. which manufacterur has the most options for the overall years and the individual years?**

```
SELECT  
  make AS vehicle_make_overall, -- change for each year 2022, 2023, and 2024
  COUNT(make) AS vehicle_count
FROM my.project
WHERE
  year BETWEEN 2022 and 2024 -- change to be year = 2022 and then 2023, and 2024
GROUP BY  
  make
ORDER BY
  vehicle_count DESC
```
<img width="407" alt="image" src="https://github.com/user-attachments/assets/62cc2b91-35fc-47bf-ba70-7986423e54c1">
<img width="408" alt="image" src="https://github.com/user-attachments/assets/c6f0996c-7d89-4cd9-ae26-29bfb63e8125">
<img width="400" alt="image" src="https://github.com/user-attachments/assets/b2af3328-3a13-4d9d-9ba5-18ca51915b6e">
<img width="407" alt="image" src="https://github.com/user-attachments/assets/11345e91-93f8-4d15-93c1-462d905e083f">

-----
**Conclusion**

After adding the additional data and filtering out for the preferenced add-on features, 26 vehicles remained
Of those 26 results, the year with the most vehicle options was a tie between 2022 and 2023 with nine options each. 2024 wasn't far behind with eight options.
The make (manufacturers/car brands) with the most options over the three years was Ford
