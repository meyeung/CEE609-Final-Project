# CEE609 Final Research Project
This repository contains code for the CEE609 Final Research Project
 
The project investigates how coral reef nutrient levels change after bleaching events using data obtained from satellite imagery. The aim of the investigation is to determine the coral reef conditions the year after a bleaching event has occured. 

## Introduction

### Background 
Coral reefs have become a growing focus of environmental research due to their ecological importance and vulnerability to various stressors. Global warming, bleaching events, and fluctuating nutrient levels are among the critical challenges threatening reef ecosystems. Efforts to preserve coral reef health and foster their growth are increasingly prioritized, given their role in supporting marine biodiversity and local economies. The Great Barrier Reef (GBR), the largest coral reef system in the world, has been a central subject of scientific investigation. Its vast size and ecological significance make it an ideal case study for understanding the dynamics of reef health. This research aims to develop a predictive model to analyze and predict changes in nutrient levels within the GBR over time. Satellite imagery will be utilized to extract data on key biochemical properties. This study will specifically focus on chlorophyll (CHL) levels, as they are a primary indicator of nutrient health and play a critical role in understanding the ecological state of coral reef systems. Lower chlorophyll levels are preferable because they suggest a more balanced ecosystem where algae growth is controlled, allowing corals to receive the necessary light and nutrients for survival and growth. Low chlorophyll levels are often associated with clearer water, promoting healthier coral populations and supporting reef resilience. Meanwhile, higher chlorophyll levels are typically associated with excess nutrients in the water, often from land runoff or other disturbances. This can lead to algal blooms, which compete with corals for light and nutrients, potentially suffocating the corals and preventing them from recovering from bleaching events. Therefore, maintaining or reducing chlorophyll levels is critical for the recovery and long-term health of coral reefs after bleaching events. By analyzing CHL levels, this study seeks to contribute to more effective conservation strategies and management practices for sustaining reef ecosystems.

### Past Efforts
Remote sensing has become an essential tool in the global monitoring and management of coral reefs, offering valuable insights into their composition, health, and the environmental conditions affecting them. Mumby *et al*. (2004) provides a comprehensive review of the capabilities and limitations of remote sensing technologies for mapping coral reefs worldwide$^1$. The authors highlight the wide range of ecological and environmental attributes that can be measured, including coral species, algal cover, reef community structure, sea surface temperature (SST), salinity, and ultraviolet radiation. The review emphasizes that while optical sensors are limited in turbid waters, active sonar sensors offer unique advantages in deeper waters and for mapping seabed structures. Additionally, the spectral resolution of sensors is considered more critical than spatial resolution for accurately identifying and distinguishing reef communities. This review demonstrates the growing importance of remote sensing in understanding coral reef ecosystems and supporting management decisions.

Expanding on this, Hedley et al. (2016) offers a more recent overview of coral reef remote sensing, focusing on its application to monitoring reef composition, environmental parameters, and management objectives. The authors discuss global and regional initiatives, such as the Reef Check and the Atlantic and Gulf Rapid Reef Assessment (AGRRA) programs, and the utility of moderate-resolution satellites like Landsat and Sentinel-2 for mapping and monitoring reefs. They emphasize the importance of normalizing imagery to account for atmospheric and environmental factors when detecting coral bleaching, as spectral confusion with sand can obscure accurate assessments. Additionally, they highlight how remote sensing data, when post-processed, can provide insights into critical ecological processes, ecosystem services, and environmental threats, such as ocean acidification and solar radiation. They also point out that only a small portion of the GBR is field-surveyed, and autonomous systems are likely to play a larger role in future monitoring efforts. The integration of sonar and satellite data is crucial for comprehensive, large-scale reef management. Collectively, these studies underscore the significant role of remote sensing in global coral reef research, offering innovative tools for conservation, monitoring, and adaptive management.

Numerous programs have been established to investigate and protect the health of the GBR, with remote sensing playing a central role in monitoring and managing the ecosystem. Devlin et al (2015). explored the impacts of nutrient enrichment, turbidity, sedimentation, and pesticides on the resilience of the GBR, emphasizing the combined pressures from extreme weather and climate change. Their study utilizes the Marine Monitoring Program (MMP), which integrates in situ sampling and satellite imagery to assess water quality and model contaminant transport. The research also connects nutrient enrichment to Crown-of-Thorns starfish outbreaks and highlights the importance of combining hydrodynamic and biogeochemical models with remote sensing data for effective water quality management. Baird et al. (2016) developed an optical model to assess human impacts on water clarity in the GBR, simulating reflectance based on biogeochemical properties and validating the model with MODIS data. Their model effectively captured sediment dispersion during Tropical Cyclone Yasi, providing valuable insights into water clarity and phytoplankton dynamics.

Additionally, the Commonwealth Scientific and Industrial Research Organisation (CSIRO), in collaboration with the GBR Marine Park Authority (GBRMPA), advanced reef mapping procedures using Landsat data to produce rectified imagery and thematic products on bathymetry, geomorphological zones, and environmental parameters. Remote sensing has proven essential for large-scale reef surveying and management, aiding in oceanographic studies and sediment research. Liu et al. (2003) analyzed the 2002 GBR bleaching event using NOAA's Coral Reef Watch products, such as SST HotSpot and Degree Heating Week (DHW), to measure thermal stress and predict coral bleaching. Their study revealed that the 2002 event was more severe than the 1998 bleaching, where the tools provided early warnings of widespread coral bleaching. Liu et al. (2003) also called for further research into other factors such as light, salinity, pollution, and ocean currents, which affect the GBR’s health. These studies emphasize the growing significance of remote sensing for monitoring, understanding, and managing the complex environmental challenges facing the Great Barrier Reef.



## Data and Methods 



## Results

## Discussion


## Conclusion 









## Data Download and Pre-process Code
Data is obtained from [https://oceancolor.gsfc.nasa.gov/13] as txt files containing urls in each line. Code cycles through each file and prepares data as a numpy array for further processing. 

All text files used by the DataDownload.ipynb notebook can be found in /DataSource/

The authors would like to acknowledge the Ocean Biology Processing Group (OBPG) and the Ocean Biology Distributed Active Archive Center (OB.DAAC) at NASA’s Goddard Space Flight Center for providing data, technical assistance, and/or review support, which greatly contributed to the success of this work. Their contributions were instrumental in facilitating the research and ensuring data integrity.

Data Citations: 

NASA Ocean Biology Processing Group. (2024). Aqua MODIS instrument Level 3&4 Browser. Retrieved from https://oceancolor.gsfc.nasa.gov/showimages/MODISA/IMAGES

## Model Training and Validation Code
The code utilizes outputs from DataDownload.ipynb to train and validate a model. Data from the 2016 and 2017 Great Barrier Reef (GBR) bleaching event and 2019 CHL levels are used to train the model. Then, the 2022 and ongoing 2024 bleaching events are fed into the model to predict future 2025 CHL levels. 

Output figures: 
* Scatterplots for the variables used to train the model 
* Comparison between true and predicted 2019 CHL levels to visualize model performance
* Scatterplots for the variables used to predict 2025 CHL levels 
* Comparison between 2024 and predicted 2025 CHL levels to visualize any reef improvemenet or deterioration 
