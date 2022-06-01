# Bike-Sharing_Demand_Prediction

---
## <b> Abstract: </b>

Bike sharing as we know is a transport service primary focus to lend conventional or electrical bikes to an individual or a group of individuals in order to let them travel in city or outskirt in rent for an hour, a day or for a month depending on the needs.



In market share we can see that Bike Sharing system has a global market share which was valued around 3.39 billion Dollars in 2019 and is projected to grow to 6.98 Billion Dollars by 2027 with a compound annual growth rate of around 14% indicatively from 2020 to 2027.



Several factors such as low bike rent, increase in capital investments,introduction of e-bikes in the market, technological advancement and government schemes for development of several bike-sharing infrastructure has increased the overall market share and led to the introduction of several opportunities during the forecasted year. However, rise in bike theft and huge initial investment are some of the key factors in order to hinder expected market growth.



Keywords: *Bike-Sharing, Data Mining, Predictive Analysis, Linear Regression, Machine Learning.*

## **Introduction:**

Bike sharing system demand nowadays is increasing in proportional manners globally. This system has gained a lot of  attention with its cost effective system and easy to use nature. This system has already attracted a huge customer base globally like in South Korea, São Paulo ,China and Australia.
Bike sharing system generally rents bikes on an hour, day and month basis and is generally based on static pricing inclusive of hour,days or month. Because of its affordability and easy renting system anyone can commute on arrival. 
According to our problem our main aim is to build a predictive model so as to find the number of bikes rented based on the given dataset.


## <b> Problem Description </b>

Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.

## <b> Data Description </b>

The dataset contains weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, Snowfall, Rainfall), the number of bikes rented per hour and date information.


## <b>Attribute Information: </b>

* Date : year-month-day
* Rented Bike count - Count of bikes rented at each hour
* Hour - Hour of he day
* Temperature-Temperature in Celsius
* Humidity - %
* Windspeed - m/s
* Visibility - 10m
* Dew point temperature - Celsius
* Solar radiation - MJ/m2
* Rainfall - mm
* Snowfall - cm
* Seasons - Winter, Spring, Summer, Autumn
* Holiday - Holiday/No holiday
* Functional Day - NoFunc(Non Functional Hours), Fun(Functional hours)

## **Feature Description**


* Date : Date feature which is str type is needed to convert it into Datetime format DD/MM/YYYY.The new feature extracted from Date are Day, Month and year
* Rented Bike Count : Number of bike rented which is our Dependent variable according to our problem statement which is int type.
* Hour: Hour feature which is in 24 hour format which tells us number bike rented per hour is int type.
* Temperature(°C): Temperature feature which is in celsius scale(°C) is Float type.
* Humidity(%): Feature humidity in air (%) which is int type.
* Wind speed (m/s) : Wind Speed feature which is in (m/s) is float type.
* Visibility (10m): Visibility feature which is in 10m, is int type.
* Dew point temperature(°C): Dew point Temperature in (°C) which tells us temperature at the start of the day is Float type.
* Solar Radiation (MJ/m2): Solar radiation or UV radiation is Float type.
* Rainfall(mm): Rainfall feature in mm which indicates 1 mm of rainfall which is equal to 1 litre of water per metre square is Float type.
* Snowfall (cm): Snowfall in cm is Float type. Seasons: Season, in this feature four seasons are present in data is str type.
* Holiday: whether no holiday or holiday can be retrieved from this feature is str type.
* Functioning Day: Whether the day is Functioning Day or not can be retrieved from this feature is str type.
* Weekend : Weekend extracted from Day 1 when the day is Saturday or Sunday while 0 when weekdays 

## **Conclusion**:-

1. In summer season highest number of bike was rented as compared to other seasons with count touching at 3500 while in winter season lowest number of bike was rented touching the count of close to just 1000. From this we can assume that people tends to rent more bikes in summer as compare to other seasons also people tends to rent less bike in winter season.
2. During working day people tend to rent more bikes as around 3500 from this we can assume that on holidays people tends to rent less bike.
3. Also we can see people tends to rent less or no bike during no functioning day.
4. In Hour vs Rented Bike Count we can see that during 18:00 Hrs(i.e 6:00 PM) highest number of bike was rented as compared to 5:00 Hrs(i.e 5:00 AM). This means people tends to rent less bikes at early morning.
5. In Rainfall vs Rented Bike Count and similarly with Snowfall vs Rented Bike Count we can see that people tend to rent highest number of bikes during 0.00mm of Rainfall or no rainfall and 0.00cm of snowfall or no snowfall as compared to when there is actully rainfall or snowfall. In other words people rent less bikes or no bikes with the increase of rainfall or snowfall.
6. In month vs Rented Bike Count we can see that people tends to rent more bike in 6 or june month as compared to less bike during dec or january.From this we can assume that people tends to rent more bikes in summer as compared to winter.
7. In weekend vs Rented Bike count we can see that people tends to rent more bike during weekdays as compared to weekends.
8. In Average Bike Rented vs Hour we can clearly see that at 6:00 PM average number of bike rented by the people was 1550. While at 00.00 or at midnight average bike rented was lowest with just around 550 bikes.
9. In Average Bike Rented vs Month we can clearly see that Average Bike rented in July was highest around 1250 and Average Bike Rented during month of February was the Lowest with just 200 average bike.
10. After applying linear regression model, we got R2 score of 0.779 for training data and R2 score of 0.774 for test data, which signifies that model is optimally fit on both training and test data i.e. no overfitting is seen.
11. Therefore, for even better fit, we applied polynomial regression model with degree = 2, we got R2 score of 0.933 for training data and 0.90 for test data
12. We also tried Tree based classifiers for our data, we applied Decision Tree Regressor, since decision tree is prone to overfit, we gave certain parameters like maximum depth of the tree, maximum leaf nodes etc, with that we  we got R2 score of 0.835 for training data and 0.803 for test data which is less than polynomial regression.
13. To get better accuracy on tree based model, we applied Random forest with n_estimator as 180 and with maximum depth as 13, with that we got R2 score of 0.888 for training data and 0.875 for test data.
14. Finally, we applied Gradient boost with parameters selected after grid search which resulted in highest R2 score of 0.958 for training data and 0.933 for test data with very less mean squared error of 6 and 10 in training as well as in test data.
15.Also we can see from SHAP summary that high Hour_18 value increasing prediction. Also we can see low Snowfall value increasing prediction and it is a common phenomenon in all the models.
16.Lastly, In bar graph from SHAP we can see Winter has the highest feature value while Wind Speed has the Lowest shap value.We can conclude that Hour_21,Hour_8 and Wind Speed is not contributing in Decision Tree,Random Forest and Gradient Boost in model prediction.


