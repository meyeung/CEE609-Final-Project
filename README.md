# CEE609 Final Research Project
This repository contains code for the CEE609 Final Research Project
 
The project investigates how coral reef nutrient levels change after bleaching events using data obtained from satellite imagery. The aim of the investigation is to determine the coral reef conditions the year after a bleaching event has occured. 



## Introduction
This section gives background regarding coral reefes, and prior efforts taken in reef investigation. The gaps in the field are identified and an overarching research question is posed.

### Background 
Coral reefs have become a growing focus of environmental research due to their ecological importance and vulnerability to various stressors. Global warming, bleaching events, and fluctuating nutrient levels are among the critical challenges threatening reef ecosystems. Efforts to preserve coral reef health and foster their growth are increasingly prioritized, given their role in supporting marine biodiversity and local economies. The Great Barrier Reef (GBR), the largest coral reef system in the world, has been a central subject of scientific investigation. Its vast size and ecological significance make it an ideal case study for understanding the dynamics of reef health. This research aims to develop a predictive model to analyze and predict changes in nutrient levels within the GBR over time. Satellite imagery will be utilized to extract data on key biochemical properties. This study will specifically focus on chlorophyll (CHL) levels, as they are a primary indicator of nutrient health and play a critical role in understanding the ecological state of coral reef systems. Lower chlorophyll levels are preferable because they suggest a more balanced ecosystem where algae growth is controlled, allowing corals to receive the necessary light and nutrients for survival and growth. Low chlorophyll levels are often associated with clearer water, promoting healthier coral populations and supporting reef resilience. Meanwhile, higher chlorophyll levels are typically associated with excess nutrients in the water, often from land runoff or other disturbances. This can lead to algal blooms, which compete with corals for light and nutrients, potentially suffocating the corals and preventing them from recovering from bleaching events. Therefore, maintaining or reducing chlorophyll levels is critical for the recovery and long-term health of coral reefs after bleaching events. By analyzing CHL levels, this study seeks to contribute to more effective conservation strategies and management practices for sustaining reef ecosystems.

### Past Efforts
Remote sensing has become an essential tool in the global monitoring and management of coral reefs, offering valuable insights into their composition, health, and the environmental conditions affecting them. Mumby *et al*. (2004) provides a comprehensive review of the capabilities and limitations of remote sensing technologies for mapping coral reefs worldwide [1]. The authors highlight the wide range of ecological and environmental attributes that can be measured, including coral species, algal cover, reef community structure, sea surface temperature (SST), salinity, and ultraviolet radiation. The review emphasizes that while optical sensors are limited in turbid waters, active sonar sensors offer unique advantages in deeper waters and for mapping seabed structures. Additionally, the spectral resolution of sensors is considered more critical than spatial resolution for accurately identifying and distinguishing reef communities. This review demonstrates the growing importance of remote sensing in understanding coral reef ecosystems and supporting management decisions.

Expanding on this, Hedley *et al*. (2016) offers a more recent overview of coral reef remote sensing, focusing on its application to monitoring reef composition, environmental parameters, and management objectives [2]. The authors discuss global and regional initiatives, such as the Reef Check and the Atlantic and Gulf Rapid Reef Assessment (AGRRA) programs, and the utility of moderate-resolution satellites like Landsat and Sentinel-2 for mapping and monitoring reefs. They emphasize the importance of normalizing imagery to account for atmospheric and environmental factors when detecting coral bleaching, as spectral confusion with sand can obscure accurate assessments. Additionally, they highlight how remote sensing data, when post-processed, can provide insights into critical ecological processes, ecosystem services, and environmental threats, such as ocean acidification and solar radiation. They also point out that only a small portion of the GBR is field-surveyed, and autonomous systems are likely to play a larger role in future monitoring efforts. The integration of sonar and satellite data is crucial for comprehensive, large-scale reef management. Collectively, these studies underscore the significant role of remote sensing in global coral reef research, offering innovative tools for conservation, monitoring, and adaptive management.

Numerous programs have been established to investigate and protect the health of the GBR, with remote sensing playing a central role in monitoring and managing the ecosystem. Devlin *et al* (2015). explored the impacts of nutrient enrichment, turbidity, sedimentation, and pesticides on the resilience of the GBR, emphasizing the combined pressures from extreme weather and climate change [3]. Their study utilizes the Marine Monitoring Program (MMP), which integrates in situ sampling and satellite imagery to assess water quality and model contaminant transport. The research also connects nutrient enrichment to Crown-of-Thorns starfish outbreaks and highlights the importance of combining hydrodynamic and biogeochemical models with remote sensing data for effective water quality management. Baird *et al*. (2016) developed an optical model to assess human impacts on water clarity in the GBR, simulating reflectance based on biogeochemical properties and validating the model with MODIS data [4]. Their model effectively captured sediment dispersion during Tropical Cyclone Yasi, providing valuable insights into water clarity and phytoplankton dynamics.

Additionally, the Commonwealth Scientific and Industrial Research Organisation (CSIRO), in collaboration with the GBR Marine Park Authority (GBRMPA), advanced reef mapping procedures using Landsat data to produce rectified imagery and thematic products on bathymetry, geomorphological zones, and environmental parameters [5]. Remote sensing has proven essential for large-scale reef surveying and management, aiding in oceanographic studies and sediment research. Liu *et al*. (2003) analyzed the 2002 GBR bleaching event using NOAA's Coral Reef Watch products, such as SST HotSpot and Degree Heating Week (DHW), to measure thermal stress and predict coral bleaching [6]. Their study revealed that the 2002 event was more severe than the 1998 bleaching, where the tools provided early warnings of widespread coral bleaching. Liu *et al*. (2003) also called for further research into other factors such as light, salinity, pollution, and ocean currents, which affect the GBR’s health. These studies emphasize the growing significance of remote sensing for monitoring, understanding, and managing the complex environmental challenges facing the Great Barrier Reef.

### Research Question
While previous studies highlight the immediate impact on coral health, the long-term effects on nutrient dynamics, especially chlorophyll, are unclear. The project aims to use satellite imagery to track these changes and build a predictive model for reef health. This work will contribute to understanding how nutrient levels impact coral recovery, aligning with existing literature that emphasizes the need to monitor post-bleaching conditions for better conservation and management.

This project investigates how coral reef nutrient levels, particularly chlorophyll concentrations, will change in the year following the 2024 GBR bleaching event. This question aims to test the hypothesis that increased chlorophyll levels in coral reefs one year after bleaching events will negatively affect coral health, based on satellite imagery data and existing knowledge of nutrient dynamics.



## Data and Methods
This section details how the satellite imagery will be aquired and post-processed. Details regarding the regression model to be trained are also given.  

### Data source and processing methods 
The NASA Ocean Color Level 3 Browser is a public open source data set that provides daily, 8-day, monthly, and yearly data for over 10 ocean color products, including chlorophyll concentration, sea surface temperature, and more. All satellite imagery can be accessed and downloaded from the NASA Ocean Color Level 3 Browser data (https://oceancolor.gsfc.nasa.gov). The recommended citation for each dataset is as follows: 
NASA Ocean Biology Processing Group. (2024). Aqua MODIS instrument Level 3&4 Browser. 

The world image is cropped to select regions, such as the Great Barrier Reef, and the Aqua-MODIS satellite is utilized to acquire all datasets. This tool allows us to visualize nutrient levels before and after bleaching events, and download high-resolution data across various time periods, supporting oceanographic and environmental research. The data has also been continuously collected since 2002, giving a temporally rich dataset. 
The validation dataset will contain historical nutrient levels of chlorophyll (CHL), particulate organic carbon (POC), particulate inorganic carbon (PIC), total absorption at 555nm (WLA), and photosynthetically available radiation (PAR) around the time of bleaching events. This will serve as inputs to train the predictive model. The model is then evaluated by comparing its predicted CHL levels to existing satellite imagery for that time. The model will be trained using historical GBR data from 2015 to 2019. Following this, the model will be subjected to GBR data from 2021 to 2024 to predict CHL levels for 2025, and patterns and trends elucidated from the model will be evaluated. All pre- and post-processing code is written in Jupyter Notebook and included. 
Jupyter Notebook is an open-source, interactive web-based environment that allows users to create and share documents containing live code, equations, visualizations, and narrative text. It supports multiple programming languages, including Python, R, and Julia, making it a versatile tool for data analysis, machine learning, and scientific computing. The satellite data files of the parameters previously mentioned (CHL, etc.) will be uploaded to the notebook and each parameter will be mapped and examined. The main output will be the prediction of CHL levels in the year 2025.

### Model description

The software can be applied to past datasets to validate its predictive ability by comparing its outputs to the most recent data. The validation dataset will contain historical nutrient levels of CHL, POC, PIC, WLA, and PAR. The software’s predictive ability will be validated using historical GBR data. 
The study trains a Ridge regression model using the listed predictor variables from 2015 to 2018 to learn patterns and trends. The 2019 prediction is then compared with satellite imagery collected in 2019 to assess accuracy by evaluating the differences between predictions and actual outcomes of nutrient levels after bleaching events. The Mean Absolute Error ($\text{MAE}$), Mean Square Error ($\text{MSE}$), and the $R^2$ value are also computed as 

$$
\text{MAE} = \frac{1}{n} \sum_{i=1}^n | y_i - \hat{y}_i |, 
$$

$$
\text{MSE} = \frac{1}{n} \sum_{i=1}^n ( y_i - \hat{y}_i )^2, 
$$

$$
R^2 = 1 - \frac{ \sum_{i=1}^n ( y_i - \hat{y}_i )^2 } { \sum_{i=1}^n } .
$$

$$
\overline{a}
$$

$$
R^2 = 1 - \frac{\sum_{i=1}^n (y_i - \hat{y}_i )^2}{\sum_{i=1}^n ( y_i - \overline{y})^2}
$$

where $y_i$ are the predicted values, $\hat{y}_i$ are the predicted values, and $\overline{(\cdot)}$ denotes a time-averaged quantity. 
Data from 2021 to 2024 is then used to predict future trends in 2025. If CHL levels are predicted to increase in 2025, this would indicate a decline in reef health in the following year, while lower CHL levels in 2025 would suggest the reef will begin the healing process. 





## Results



## Discussion


## Conclusion 






## Bibliography 
[1] P. J. Mumby, W. Skirving, A. E. Strong, J. T. Hardy, E. F. LeDrew, E. J. Hochberg, R. P. Stumpf, and L. T. David, “Remote sensing of coral reefs and their physical environment,” Marine pollution bulletin, vol. 48, no. 3-4, pp. 219–228, 2004
[2] J. D. Hedley, C. M. Roelfsema, I. Chollett, A. R. Harborne, S. F. Heron, S. J. Weeks, W. J. Skirving, A. E. Strong, C. M. Eakin, T. R. Christensen, et al., “Remote sensing of coral reefs for monitoring and management: a review,” Remote Sensing, vol. 8, no. 2, p. 118, 2016
[3] M. J. Devlin, C. Petus, E. Da Silva, D. Tracey, N. H. Wolff, J. Waterhouse, and J. Brodie, “Water quality and river plume monitoring in the great barrier reef: an overview of methods based on ocean colour satellite data,” Remote Sensing, vol. 7, no. 10, pp. 12909– 12941, 2015
[4] M. E. Baird, N. Cherukuru, E. Jones, N. Margvelashvili, M. Mongin, K. Oubelkheir, P. J. Ralph, F. Rizwi, B. J. Robson, T. Schroeder, et al., “Remote-sensing reflectance and true colour produced by a coupled hydrodynamic, optical, sediment, biogeochemical model of the great barrier reef, australia: comparison with satellite data,” Environmental modelling & software, vol. 78, pp. 79–96, 2016
[5] D. L. Jupp, K. K. Mayo, D. A. Kuchler, D. V. R. Claasen, R. A. Kenchington, and P. R. Guerin, “Remote sensing for planning and managing the great barrier reef of australia,” Photogrammetria, vol. 40, no. 1, pp. 21–42, 1985
[6] G. Liu, A. E. Strong, and W. Skirving, “Remote sensing of sea surface temperatures during 2002 barrier reef coral bleaching,” Eos, Transactions American Geophysical Union, vol. 84, no. 15, pp. 137–141, 2003



