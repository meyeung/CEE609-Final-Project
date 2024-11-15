# CEE609 Final Research Project
This repository contains code for the CEE609 Final Research Project
 
The project investigates how coral reef nutrient levels change after bleaching events using data obtained from satellite imagery. The aim of the investigation is to determine the coral reef conditions 5 years after a bleaching event has occured. 

## Data Download and Pre-process Code
Data is obtained from [https://oceancolor.gsfc.nasa.gov/13] as txt files containing urls in each line. Code cycles through each file and prepares data as a numpy array for further processing. 

All text files used by the DataDownload.ipynb notebook can be found in /TxtFiles/

Data Citations: 
xxx

## Model Training and Validation Code
The code utilizes outputs from DataDownload.ipynb to train and validate a Linear Regression model. Data from the 2016 and 2017 Great Barrier Reef (GBR) bleaching event and 2018 CHL levels are used to train the model. Then, the 2022 and ongoing 2024 bleaching events are fed into the model to predict future 2025 CHL levels. 


