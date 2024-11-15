# CEE609 Final Research Project
This repository contains code for the CEE609 Final Research Project
 
The project investigates how coral reef nutrient levels change after bleaching events using data obtained from satellite imagery. The aim of the investigation is to determine the coral reef conditions 5 years after a bleaching event has occured. 

## Data Download and Pre-process Code
Data is obtained from [https://oceancolor.gsfc.nasa.gov/13] as txt files containing urls in each line. Code cycles through each file and prepares data as a numpy array for further processing. 

All text files used by the DataDownload.ipynb notebook can be found in /TxtFiles/

Data Citations: 
xxx

## Model Training and Validation Code
The code utilizes outputs from DataDownload.ipynb to train and validate a model using data from the Red Sea Coral Reef. The model is then used to predict the state of the coral reef nutrient levels five years after the 2024 bleaching event. 
