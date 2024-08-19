## 1. Vehicle Model Research

Here I worked with the data to observe which make (manufacturers/car brands) and which year (2022 - 2024) will most likely be the future vehicle.

-----
1. Which make (manufacturers/car brands) offers the most vehicle options?
2. Which year offers the most vehicle options?
3. Which make (manufacturers/car brands) of each year offers the most vehicle options?

-----
**1. Which make (manufacturers/car brands) offers the most vehicle options?**

```
SELECT  
  make,
  COUNT(make) AS make_count
FROM my.project
GROUP BY
  make
ORDER BY
  make_count DESC
LIMIT 5
```
<img width="400" alt="image" src="https://github.com/user-attachments/assets/583545c5-6f52-41da-aa3f-8291333a7692">

![image](https://github.com/user-attachments/assets/22578ca6-8375-48a1-896e-37f0dcf25265)

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
<img width="323" alt="image" src="https://github.com/user-attachments/assets/1ce54f1e-5ef3-4813-a60f-4779d68df267">

-----
**3. Which make (manufacturers/car brands) of each year offers the most vehicle options?**

```
SELECT  
  make AS vehicle_make_2022, -- change year to 2023, then 2024
  COUNT(make) AS vehicle_count
FROM my.project 
WHERE
  year =2022 -- change year to 2023, then 2024
GROUP BY 
  vehicle_make_2022 -- change year to 2023, then 2024
ORDER BY
  vehicle_count DESC
LIMIT 5
```
<img width="397" alt="image" src="https://github.com/user-attachments/assets/d3921c9a-3ec8-4502-8d16-2fd985b890b4">
<img width="399" alt="image" src="https://github.com/user-attachments/assets/b0ff9d35-f1b9-4f48-862e-cb823eda2e49">
<img width="399" alt="image" src="https://github.com/user-attachments/assets/58375162-68b2-4ad6-9bf6-426770043919">


-----

<img width="601" alt="image" src="https://github.com/user-attachments/assets/08a57d58-9f0a-4249-948d-caa211f8ee7c">

----
**Conclusion**

In observing the data, BMW and Porsche offer the most options for vehicles for all three years combined as well as each individual year. 
The year that offers the most vehicle options is 2022.
