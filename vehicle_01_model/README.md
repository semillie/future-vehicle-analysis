## 1. Vehicle Model Research

Here we will be working with the data to observe which make (manufacturers/car brands) and which year (2022 - 2024) will most likely be our future vehicle

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
<img width="400" alt="vehicle_model_count" src="https://github.com/user-attachments/assets/50fca359-df23-4e46-a4a8-3f208be06db3">

![vehicle_model_count](https://github.com/user-attachments/assets/f851c116-16bd-4fd2-88be-7443a4bba1d4)

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
<img width="323" alt="vehicle_model_yearly" src="https://github.com/user-attachments/assets/2a948353-dfab-4761-8203-018fc2335d0c">

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
<img width="397" alt="model_count_2022" src="https://github.com/user-attachments/assets/45a678ba-e8ea-4f2c-8014-e66beae657ad"><img width="399" alt="model_count_2023" src="https://github.com/user-attachments/assets/0e8e315b-6fc7-4bc8-9e33-4c5cc4b6218c"><img width="399" alt="model_count_2024" src="https://github.com/user-attachments/assets/0759990a-3cc9-4241-9095-833826c213de">

<img width="601" alt="vehicle_model_year" src="https://github.com/user-attachments/assets/39246d32-b79e-4b59-a7f5-5f94bd26a38c">

----
**Conclusion**

In observing the data, BMW and Porsche offer the most options for vehicles for all three years combined as well as each individual year. 
The year that offers the most vehicle options is 2022.
