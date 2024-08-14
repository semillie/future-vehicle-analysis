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
<img width="405" alt="vehicle_final_make" src="https://github.com/user-attachments/assets/00d2c489-9f1c-466c-b163-cf574412a182">

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
<img width="329" alt="vehicle_final_year" src="https://github.com/user-attachments/assets/af3116f6-0ecc-4c6b-bb02-954451221676">

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
<img width="410" alt="make_final_2022" src="https://github.com/user-attachments/assets/937ffbec-bc23-44bf-8755-147bb6b19527"><img width="404" alt="make_final_2023" src="https://github.com/user-attachments/assets/67c09a4f-946f-4c65-98d3-f7f2d5cae34d"><img width="414" alt="make_final_2024" src="https://github.com/user-attachments/assets/c46757ac-cb3f-410f-9e08-2f06f14b6b98">


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
<img width="726" alt="top5_price" src="https://github.com/user-attachments/assets/93cc9a1e-51dc-4c77-921c-ac0b187ecdfa">

-----
**Conclusion**

The make (manufacturers/car brands) that ended up offering the most options for the future vehicle ended up being Ram.
The year that offered the most options for the top five future vehicle options is 2022, with six options over all.

However, as seen below, 2022 GMC and 2023 Toyota ended up becoming the top two options for even though Ram had the highest chance.

<img width="1278" alt="top5_full_specs" src="https://github.com/user-attachments/assets/aec0d63b-4d29-4f60-b470-178332b3274a">
