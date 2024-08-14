## 5. Vehicle Add-On Feature Research

By minimizing the future vehicle list by requirements and preferences, we are left with 46 results of what the future vehicle could be. 

To further determine the result, we acquired further data for add-on features.
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
<img width="208" alt="vehicle_feature_count" src="https://github.com/user-attachments/assets/159b35e8-6fc8-4f79-b117-5de1401d44a8">

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
<img width="327" alt="year_feature_count" src="https://github.com/user-attachments/assets/cbd29ba3-c473-4897-b2be-270e21e3b444">

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
<img width="407" alt="make_feature_count" src="https://github.com/user-attachments/assets/0446259f-ff3c-4c6b-9ee1-cd94d2dc9b6d">
<img width="408" alt="feature_make_2022" src="https://github.com/user-attachments/assets/24dba3d2-dd13-40d8-af33-6ada3b2aec19"><img width="400" alt="feature_make_2023" src="https://github.com/user-attachments/assets/03716420-ca4d-4f30-9cba-aef71302e0ed"><img width="407" alt="feature_make_2024" src="https://github.com/user-attachments/assets/bd593da7-7f2a-4f65-b290-3a81ae3391e6">


-----
**Conclusion**

After adding the additional data and filtering out for the preferenced add-on features, it left us with 26 results.
Of those 26 results, the year with the most vehicle options was a tie between 2022 and 2023 with nine options each. 2024 wasn't far behind with eight options.
The make (manufacturers/car brands) with the most options over the three years was Ford.
