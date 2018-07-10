# Machine_Learning_for_Predicting_Energy_Consumption

<h2>Introduction</h2>

As interest in IOT and sensors pick up steam, companies are trying to build algorithms and systems to understand consumer behavior to help them make better decisions. One such application is energy modeling. Though, most consumers are aware of their aggregate consumption of energy, few are aware of how and where energy is consumed. With increasing sensors in equipment, it is becoming easier to find out which equipment/instruments consume the most power. I came across a recent paper and dataset and interested in building various machine learning models that could contribute to understanding energy usage by appliances and the attributes that contribute to aggregate energy usage. With the knowledge of energy consumed by various equipment, seasonality and attributes like temperature and humidity, a machine learning model could be used to predict aggregate energy use.

<h2><b>Details of Dataset</b></h2>
<b><h3>First Floor</h3></b><br>

![firstfloor](https://user-images.githubusercontent.com/40823735/42492844-38eb8c1c-8438-11e8-8446-87931d2ff65d.png)<br>
<i>Temperature and Humidity sensors position. The blue circles indicate the sensor number. The coordinator (C) is positioned around the middle of the house, near the dining room table. (For interpretation of the references to color in this figure legend, the reader is referred to the web version of the article.)</i><br>

<b><h3>Second Floor</h3></b><br>
![second floor](https://user-images.githubusercontent.com/40823735/42492368-7570ba24-8436-11e8-983f-dcea4adb36f4.png)<br>
<i>Location of the Temperature and Humidity sensors. The blue circles indicate the sensor number. Sensor node 6 measures the exterior conditions. (For interpretation of the references to color in this figure legend, the reader is referred to the web version of the article.)</i><br>
<b><h3>Variable Description</h3></b><br>
<b>date, time year-month-day hour:minute:second</b><br>
<b>Appliances</b>, energy use in <b>Wh</b><br>
<b>lights</b>, energy use of light fixtures in the house in <b>Wh</b><br>
<b>T1</b>, Temperature in kitchen area, in <b>Celsius</b><br>
<b>RH_1</b>, Humidity in kitchen area, in <b>%</b><br>
<b>T2</b>, Temperature in living room area, in <b>Celsius</b><br>
<b>RH_2</b>, Humidity in living room area, in <b>%</b><br>
<b>T3</b>, Temperature in laundry room area, in<b>Celsius</b><br>
<b>RH_3</b>, Humidity in laundry room area, in <b>%</b><br>
<b>T4</b>, Temperature in office room, in <b>Celsius</b><br>
<b>RH_4</b>, Humidity in office room, in <b>%</b><br>
<b>T5</b>, Temperature in bathroom, in <b>Celsius</b><br>
<b>RH_5</b>, Humidity in bathroom, in <b>%</b><br>
<b>T6</b>, Temperature outside the building (north side), in <b>Celsius</b><br>
<b>RH_6</b>, Humidity outside the building (north side), in <b>%</b><br>
<b>T7</b>, Temperature in ironing room , in <b>Celsius</b><br>
<b>RH_7</b>, Humidity in ironing room, in <b>%</b><br>
<b>T8</b>, Temperature in teenager room 2, in <b>Celsius</b><br>
<b>RH_8</b>, Humidity in teenager room 2, in <b>%</b><br>
<b>T9</b>, Temperature in parents room, in <b>Celsius</b><br>
<b>RH_9</b>, Humidity in parents room, in <b>%</b><br>
<b>To</b>, Temperature outside (from Chièvres weather station), in <b>Celsius</b><br>
<b>Pressure</b> (from Chièvres weather station), in <b>mm Hg</b><br>
<b>RH_out</b>, Humidity outside (from Chièvres weather station), in <b>%</b><br>
<b>Windspeed</b> (from Chièvres weather station), in <b>m/s</b><br>
<b>Visibility</b> (from Chièvres weather station), in <b>km</b><br>
<b>Tdewpoint</b> (from Chièvres weather station), <b>Celcius</b><br>
<b>rv1</b>, Random variable 1, <b>nondimensional</b><br>
<b>rv2</b>, Rnadom variable 2, <b>nondimensional</b><br><br>

Where indicated, data from the nearest airport weather station (Chièvres Airport, Belgium) was downloaded from a public data set from 
Reliable Prognosis, rp5.ru. Permission was obtained from Reliable Prognosis for the distribution of the 4 months of data.


<h2>Exploratory Data Analysis</h2>

![screen shot 2018-07-10 at 11 30 06 am](https://user-images.githubusercontent.com/40823735/42491949-b1131c72-8434-11e8-9462-f9798a4f3d07.jpg)
<i> The graph states that Appliances contribute to major part of energy consumption. </i><br> 

![daywise_appliances_energy_consumption](https://user-images.githubusercontent.com/40823735/42491286-ded980cc-8431-11e8-8da9-76e7598bfdda.png)<br>
<i>Energy Consumption is highest on <b>Monday</b></i><br>

![hourlyappliancesenergyconsumption](https://user-images.githubusercontent.com/40823735/42491710-97d86f74-8433-11e8-9d6e-8d91df12f1ac.png)<br>
<i>Energy Consumption is high from <b>17:00 to 19:00 hrs</b> i.e in the evening</i><br>
<i>Energy Consumption is low from <b>22:00 to 6:00 hrs</b> i.e at late night </i><br>

<h2>Prediction Algorithms with metrices</h2>

![screen shot 2018-07-10 at 12 01 45 pm](https://user-images.githubusercontent.com/40823735/42493118-360501d0-8439-11e8-99f8-7fb45ce4d560.jpg)

<h2> Feature Selection </h2>
After selecting features manually,and with the help of Correlation-matrix, Boruta, Tsfresh, Featuretools, RFE and trying them out.<br> 
The following features were selected that gives the best result- <br>
<i>hour, month, day_of_week, period, time, T4, T5, T6,T8, T9, Tdewpoint, T_out, RH_4, RH_5, RH_6, RH_7, RH_8, RH_9, Press_mm_hg</i><br>

<h2> Model Validation and Selection </h2>
<i> Cross-validation is used to validate model. After validation, Random Forest Regressor is selected as best prediction model with R2_test score <b>0.57</b> and R2_train score <b>0.94</b></i>
