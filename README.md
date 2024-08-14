# Future Vehicle Research
research using SQL to help pick out new car

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
  the original dataset held 2583 results of vehicles that were released from 2022 - 2024 with the specifications: year, make, model, number of cylinders, drivetrain, fuel type, the highway mileage per gallon, type of transmission, the size and type of vehicle, and the base model name.


Schema:
<img width="1150" alt="future_car_schema" src="https://github.com/user-attachments/assets/c41c7327-7bae-49c0-8e52-467a5f240bcb">



##### Sources
  the data that was acquired was from Environmental Projection Agency, with further research on specificications and add-ons found through Car and Driver / Hearst Autos, inc., and Kelley's Blue Book
