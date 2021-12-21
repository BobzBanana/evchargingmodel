Exploratory model for EV charging infrastructure in Singapore
With concerns about the environment and climate change, as part of the Singapore Green Plan 2030 (SGP30), the Government aims to phase out all Internal Combustion Engine (ICE) vehicles and have all vehicles run on cleaner energy by 2040. A comprehensive roadmap has been developed to encourage further EV adoption, one such initiative is the development of EV charging infrastructure to cater for the anticipated spike in the number of Electric Vehicles (EVs) on the road. However, a new problem arises: how many charging stations are required to cater for the different year-on-year EV growth rates and, more specifically, how many stations are required in each planning area in Singapore?
For my college module Spreadsheet Modelling & Analytics, my team and I set out to create an exploratory model using Microsoft Excel that can anticipate, for different EV adoption growth rates, the number of charging stations required in each planning area in Singapore.
The main output of the model would be the predicted number of charging stations required per planning area in Singapore under different scenarios.
The different scenarios are as shown:
Different possible scenarios for EV adoption rate by 2040
Different possible scenarios for EV adoption rate by 2040
Data Collection & Analysis
The following datasets were used in the creation of the model.
Annual Motor Vehicle Population By Type of Fuel Used
The dataset (MVP01–4_MVP_by_fuel.xls) is from LTA and it includes information regarding the different categories of vehicles from 2010 to 2020. Within each type of vehicle, the dataset classifies the vehicles according to fuel type. Only data regarding private car ownership will be used to reduce model complexity together with the fact that a majority of the vehicle population consists of private cars.

Private car ownership by type of fuel used
From the data above, there was no significant data on electric vehicles from 2010–2013. Therefore the model’s prediction is based on the year 2014 onwards. We will make the following predictions based off this dataset till the year 2040:
1) Total Car Population
Through the use of regression, using a linear trend line to estimate the general car population. The choice of the linear regression line was due to the year-on-year increase in privately owned vehicles reported despite record-high COE costs. Therefore, for this model, the assumption is that the growth in the number of cars in Singapore will follow a linear trend, in anticipation of more car sales in the future.
2) Total EV Growth
As per the 3 different scenarios laid out earlier, a power regression curve is used to estimate the different growth rates for each scenario. This regression curve was chosen as the power constant can be adjusted according to the different targets set out by the different scenarios, namely 10%, 30%, and 50% of the total car population within Singapore.
3) Drivetrain Mix Percentage
Drivetrain mix percentage refers to the percentage of EVs that are made up of PHEVs and BEVs. For this, a power regression curve is used to model the decrease in the percentage of PHEVs compared to the number of BEVs. The decision to use a power regression curve is due to the assumption that there will continue to be PHEVs on the road, albeit in very few numbers, therefore the curve will approach but not reach zero when extrapolated over time. This is based on existing data that shows that the number of BEVs purchased has been increasing far more than the number of PHEVs.
There is also sufficient evidence to show that users are highly encouraged to adopt BEVs as a result of the EV Early Adoption Incentive and the enhanced Vehicular Emissions Scheme (VES) by the Government that offsets the upfront cost of BEVs. Thus, while there may continue to be PHEVs in the future, it is anticipated that the majority of EVs by 2040 will be BEVs.
Residential Dwellings by Planning Area and Type of Dwelling
This dataset (residential_dwelling_by_planning_area_2020.xlsx) was obtained from SingStat and it shows the total number of the different types of residential dwellings in each planning zone and sub-planning zones in Singapore as of June 2020.

Total number of households in Singapore by district
The focus will only be on residential planning areas with HDBs, condominiums, and landed properties. Industrial estates are excluded from the project. This data is used to predict the number of households per planning area from 2020 to 2040.
To predict the growth rate of the number of households per Planning Area, we used an LN trend line. This is to simulate a situation where the number of households will eventually stagnate due to the lack of space in Singapore. Hence, a graph is plotted for the number of households in each Planning Area to get the LN function necessary to predict the different Planning Areas.
Plug-In Hybrid Electric Vehicles (PHEVs) and Battery Electric Vehicles (BEVs)
PHEVs and BEVs are the two types of electric vehicles that require charging infrastructure. The model requires reference vehicles to calculate the required number of charging stations, based on the car’s energy consumption. The Tesla Model 3 will be the point of reference for BEVs with energy consumption rated at 0.15 kWh/km.
The Toyota Prius will be the point of reference for PHEVs. As the Toyota Prius is a PHEV and not a traditional BEV, it means that it can operate on both fuel and electricity. Therefore, calculating the energy consumption of the Toyota Prius is slightly more challenging as there are different modes that the car can operate in. The Toyota Prius can go about 50 km on electricity before switching to petrol. Taking that into account, by taking the battery capacity of the Toyota Prius of 8.8kWh, and dividing it by the average distance it could travel on battery power alone, 50km. We get Energy Consumption of Toyota Prius = 8.8kwh / 50 km = 0.176 kWh/km.
Type of Charger
A standard charger will be used in the model to reduce model complexity. The AC Slow, Type 2, Single Phase charger that has a power level of 3.3kW is chosen as it falls within the nationwide electric vehicle (EV) charging standard set by the Energy Market Authority (EMA). Furthermore, such a charger best fits the needs of charging stations in residential areas.
Model Inputs
The model accepts the following inputs:
Total EV population percentage in 2040: The main inputs are the scenarios detailed above (10%, 30%, and 50%). Other percentage numbers are available as well.
Average Energy Spent (kWh/km) per PHEV and BEV: This input represents the energy consumption by PHEVs and BEVs respectively in kWh per km. This is used to calculate the energy consumption by PHEV and BEV in a year. The data for this input will be from the Tesla Model 3 and Toyota Prius as mentioned above.
Annual Vehicle Mileage (km): The average annual distance traveled by a vehicle in Singapore. This is used to calculate the energy consumption by PHEV and BEV in a year.
Type of Charger (kW): The type of charger to be/that is installed at the charging points. Different types of chargers produce different levels of power ranging from 3.3kW to 50kW. This is used for calculating the energy produced by each charger in a day. The data for this input will be from the AC Slow, Type 2, Single Phase charger as mentioned above.
Hours Spent on Charging Station in a Day: The average hours in a day that an EV spends charging. This is used to calculate the energy consumed by charging the car at a charging station.
Model Description
The influence diagram detailed below shows how the model calculates its predictions. White boxes denote model inputs while green boxes are calculated outputs.

Fig 1. How the number of EVs per planning area is calculated

Fig 2. How annual energy demand is calculated

Fig 3. How the final predicted output is calculated
Final Model
With reference to the excel model (evchargingmodel.xlsm)

Model Dashboard
The model dashboard is where users can interact with the model.

Users can change the scenario using the dropdown menu for the targeted total percentage of EV’s by 2040 and click on the green box to allow the model to compute.

After computation, on the left users can see the required number of charging stations to be built in a specific planning area in a specified year. On the right users can also see the current number of charging stations in a specific planning area for a specific year. Users can select specific planning areas and years with the dropdown menu.
Selecting the blue box brings the user to a table detailing the charging station prediction model.

The graphs are detailing the predicted growth of EVs to meet the target and the EV annual energy consumption. Each blue box when clicked directs the user to the specific sheet detailing the prediction model.
Final Thoughts
The model does suffer from inaccuracies due to a lack of historical data as EV ownership is still in its infancy in Singapore. Inaccuracies are also compounded due to the fact a standard charger and reference vehicles are used for the model which does not represent real-world scenarios of different chargers and types of vehicles. New housing estates and planning areas built in the future are also not included in this model.
Another issue is that the nature of EV ownership and charging station installation is that of a “chicken-and-egg” problem. Would a higher availability of charging infrastructure lead to more EVs on the road, or would more EVs on the road lead to an increase in the number of charging stations? The model does not account for this as the dilemma between EVs and charging stations can only be resolved on the policy level. It would not be accurate to have the model be circular referencing as the data that is referenced are predictions which will compound more inaccuracies onto the predicted values. A more viable solution to this problem would be to have policymakers facilitate the growth of the EV market while having the private sector provide the charging stations. With the government supporting the growth in EV ownership, demand for charging stations will be created which will be fulfilled by the private sector.
Overall, EV adoption is the future of transportation in Singapore and electrifying Singapore’s vehicle population will require supporting infrastructure. An exploratory model on the required charging infrastructure is therefore important in the overall technology roadmap towards electromobility in the year 2040. Such a model will drive key policy decisions towards enabling a cleaner and greener vehicle population in the future.
