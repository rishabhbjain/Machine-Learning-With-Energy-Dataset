# Machine_Learning_for_Predicting_Energy_Consumption

<h2>Introduction</h2>

As interest in IOT and sensors pick up steam, companies are trying to build algorithms and systems to understand consumer behavior to help them make better decisions. One such application is energy modeling. Though, most consumers are aware of their aggregate consumption of energy, few are aware of how and where energy is consumed. With increasing sensors in equipment, it is becoming easier to find out which equipment/instruments consume the most power. I came across a recent paper and dataset and interested in building various machine learning models that could contribute to understanding energy usage by appliances and the attributes that contribute to aggregate energy usage. With the knowledge of energy consumed by various equipment, seasonality and attributes like temperature and humidity, a machine learning model could be used to predict aggregate energy use.

<h2>Exploratory Data Analysis</h2>

![screen shot 2018-07-10 at 11 30 06 am](https://user-images.githubusercontent.com/40823735/42491949-b1131c72-8434-11e8-9462-f9798a4f3d07.jpg)
<i> From the graph it is clear that Appliances contribute to major part of energy consumption. And hence, we can analyse the features with the help of Appliances as target variable</i><br> 

![daywise_appliances_energy_consumption](https://user-images.githubusercontent.com/40823735/42491286-ded980cc-8431-11e8-8da9-76e7598bfdda.png)<br>
<i>Energy Consumption is highest on <b>Monday</b></i><br>

![hourlyappliancesenergyconsumption](https://user-images.githubusercontent.com/40823735/42491710-97d86f74-8433-11e8-9d6e-8d91df12f1ac.png)
<i>Energy Consumption is high from <b>17:00 to 19:00 hrs</b></i><br>
<i>Energy Consumption is low from <b>22:00 to 6:00 hrs</b></i><br>






