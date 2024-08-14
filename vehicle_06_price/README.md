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
<img width="328" alt="image" src="https://github.com/user-attachments/assets/3d45778b-2c14-4036-a06e-6844c701921a">

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
<img width="407" alt="image" src="https://github.com/user-attachments/assets/61740f38-4438-47dd-ba36-5ca088073075">

<img width="863" alt="image" src="https://github.com/user-attachments/assets/39f1a427-4dde-45b5-ab22-3bca25d80560">

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
<img width="1208" alt="image" src="https://github.com/user-attachments/assets/57bbb44c-49a2-4706-80c4-21182adec277">

-----

**Conclusion**

The average price for the make (manufacturers/car brands) is between $40,920 - $62,334, with the preferred price sitting midground.
However, the average price for the years is between $46,498 - $56,423, leaving the preferred price below what the average is for all three years.
Applying the preferred price range to the data results in twelve possible future vehicles.
