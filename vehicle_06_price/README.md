## 6. Vehicle Price Research

The final aspect to picking out the future vehicle would be based on price, <= 45,000

-----
1. What is the average price based on years?
2. What is the average price based on make?
3. How many vehicles meet the price preference?

-----
**1. What is the average price based on years?**

```
SELECT  
  year,
  ROUND(AVG(price),0) AS average_price
FROM my.project
GROUP BY
  year
ORDER BY
  average_price
```
<img width="328" alt="average_price_year" src="https://github.com/user-attachments/assets/5f7b50f0-5b80-46b6-86ae-2d5f5e425e31">

-----
**2. What is the average price based on make?**

```
SELECT  
  make,
  ROUND(AVG(price),0) AS average_price
FROM `crafty-acumen-421202.future_car.vehicle_full_specs` 
GROUP BY
  make
ORDER BY
  average_price
```
<img width="407" alt="average_price_make" src="https://github.com/user-attachments/assets/e8145b5c-99ec-4e09-957a-6c994630d810">

-----
**3. How many vehicles meet the price preference?**

```
SELECT  
  *
FROM my.project
WHERE
  price <= 45000
ORDER BY
  make
```
<img width="1208" alt="vehicle_final_count" src="https://github.com/user-attachments/assets/a6e86814-5499-4854-af1f-2eb192d7c583">
-----

**Conclusion**

The average price for the make (manufacturers/car brands) is between $40,920 - $62,334, with our preferred price sitting midground.
However, the average price for the years is between $46,498 - $56,423, leaving our preferred price below what the average is for all three years.
Applying the preferred price range to the data leaves us with twelve possible future vehicles.
