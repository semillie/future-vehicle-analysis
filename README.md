# Future Vehicle Research
Research using SQL to help pick out new vehicle.
Step by step analysis of **which year and which make(manufacturers/car brands) offer the most options for the future vehicle** while adding more perimeters to the data.
Furthermore, **which vehicle with the desired specifications is the most affordable**?

## Contents
- original data stored in .xlsx form
- step by step research stored in .csv form
- the sql code of each step is listed in the 'readme' of each individual file
- visuals were developed on tableau

### The Research
I compiled a list of specifications wanted for the future vehicle. I then organized the list based off which specifications were required and which were preferred. I knew that this would still leave me with a decent sized list to base a decision on, so I also included a list of possible add-on features that I would like to be included in the vehicle. The data that I was able to find for the specifications of the vehicles did not include current price or add-on features so I conducted further research.
```
Required Specs:
  - 2022 - 2024 year
  - truck
  - 4 Wheel Drive option
  - automatic transmission
```
  
```
Preferred Specs:
  - engine cylinders 6 - 8
  - Regular gas
  - highway milage per gallon >= 16
```

```
Add-On Feature Specs:
  - towing capacity >= 5500
  - apple-play
  - sunroof
  - keyless remote start
```
#### The Data
  The original dataset held 2583 results of vehicles that were released from 2022 - 2024 with the specifications: year, make, model, number of cylinders, drivetrain, fuel type, the highway mileage per gallon, type of transmission, the size and type of vehicle, and the base model name.


Schema:
<img width="1150" alt="future_car_schema" src="https://github.com/user-attachments/assets/c41c7327-7bae-49c0-8e52-467a5f240bcb">



##### Sources
  The data that was acquired from Environmental Projection Agency, with further research on specificications and add-ons found through Car and Driver / Hearst Autos, inc., and Kelley's Blue Book

### Conclusion
  At the start, without any perimeters/qualifications applied to the data, the data was showing that 2022 offered the highest chance for the future vehicle. 
  As further research and perimeters were applied, there were close calls between which year would end up offering the most options. 
  Although 2022 originally held the most options, 2024 had the most for what specifications were required. 
  In the end, the price preference for the vehicle became the tie breaker with the oldest year having the most options - thus **2022 being the choice for the future vehicle year.**
  
  As for the manufacturers/car brands that offered the most options for the future vehicle, the original top five were BMW, Porsche, Mercedes-Benz, Ford and Toyota.
  With the required preferences being applied to the data, Chevrolet had the largest number of vehicle options. 
  Although Chevrolet held the most options for the requirements, it fell behind quickly once preferred specifications were added. 
  In the end, **the manufacturer/car brand with the most options that met the full list of qualifications (as well as in each individual year), was Ram.**
 
  ***2022 Rams had the most options available for the future vehicle that met all the requirements and preferences.***
  
  Furthermore, in occurrence with price, the **2022 GMC Canyon is the most affordable option**, listed at $5,000 *lower* than the other options. ***In conclusion, 2022 did hold up to offering the most options and being the most affordable year. However, even though Ram had the most options for a manufacturer/car brand they were not the most affordable option.***

-----
<img width="1113" alt="image" src="https://github.com/user-attachments/assets/c18334ce-80dd-47a8-a67e-2047d31bedf1">
<img width="710" alt="image" src="https://github.com/user-attachments/assets/30b6ca70-af68-41a3-9fd8-c9864ef4fbe1">
