## 7. The Future Vehicle

Based on the research of the data done so far, there are twelve possible options for future vehicle.

-----
```
Future Vehicle Requirements / Preferences:
- released in 2022 - 2024
- truck
- 4wd or 4WD option
- Automatic Transmission
- 6 - 8 cylinders
- Regular fuel
- 16 or more highway mileage per gallon
- towing capacity of 5500 or higher
- apple car play add on
- sunroof
- keyless remote start add on
- priced at 45,000 or lower
```
-----
1. Which make (manufacturers/car brands) offers the most vehicle options?
2. Which year offers the most vehicle options?
3. Which make (manufacturers/car brands) of each year offers the most vehicle options?
4. What are the top five options for the future vehicle?
   
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
  vehicle_count
```
<img width="329" alt="image" src="https://github.com/user-attachments/assets/24c670d7-2ae8-4e9b-b8f4-a9f8673a475a">

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
<img width="329" alt="image" src="https://github.com/user-attachments/assets/20a3143e-e44e-4626-8ff8-8b153db948ad">

-----
**3. Which make (manufacturers/car brands) of each year offers the most vehicle options?**
```
SELECT  
  make AS vehicle_make_2022, -- change year to 2023, then 2024
  COUNT(make) AS vehicle_count
FROM my.project
WHERE
  year = 2022 -- change year to 2023, then 2024
GROUP BY
  make
ORDER BY
  vehicle_count DESC
```
<img width="410" alt="image" src="https://github.com/user-attachments/assets/6228cff2-281a-418c-a064-7a0dc39732f7">
<img width="404" alt="image" src="https://github.com/user-attachments/assets/56ecfc04-84db-4554-a085-c0ca2ca8c45b">
<img width="414" alt="image" src="https://github.com/user-attachments/assets/9c2d0e8d-1edc-45a7-8f14-ba3112149150">

---- 
**4. What are the top five options for the future vehicle?**
```
SELECT  
  year,
  make,
  model,
  price
FROM my.project
ORDER BY
  price
LIMIT 5
```
<img width="726" alt="image" src="https://github.com/user-attachments/assets/f20e84fd-bbce-4a17-9401-8ed47966a726">

-----
**Conclusion**

The make (manufacturers/car brands) that ended up offering the most options for the future vehicle ended up being Ram.
The year that offered the most options for the top five future vehicle options is 2022, with six options over all.

However, as seen below, 2022 GMC and 2023 Toyota ended up becoming the top two options for even though Ram had the highest chance.

<img width="1278" alt="image" src="https://github.com/user-attachments/assets/3fe58457-bdec-4d9f-9b1c-f88714003453">
