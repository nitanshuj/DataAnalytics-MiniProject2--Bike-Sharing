# Mini Project 2 - Bike-Sharing using Linear Regression

--------------------------------------------------------------

This was an mini-project, that I completed as a part of my Post Graduate Diploma in Data Science from Upgrad & IIIT-Bangalore. The dataset and the Problem Statement was provided to me by Upgrad.

--------------------------------------------------------------

## Business Understanding:
--------------------------------------------------------------
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short-term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all-around and stand out from other service providers and make huge profits.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:
- Which variables are significant in predicting the demand for shared bikes?
- How well those variables describe the bike demands?

Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors.

--------------------------------------------------------------

## Business Objective:
--------------------------------------------------------------
You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 

--------------------------------------------------------------

## Data Dictionary
--------------------------------------------------------------

|Column |Description |
| :- | :------------- |
|**instant** |record index |
|**dteday** |date |
|**season** |season (1 - spring :: 2 - summer :: 3 - fall :: 4 - winter) |
|**yr** |year (0: 2018, 1:2019) |
|**mnth** |month ( 1 to 12) |
|**holiday** |weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule) |
|**weekday** |day of the week |
|**workingday** |if day is neither weekend nor holiday is 1, otherwise is 0. |
|**weathersit**  | |
|  |1: Clear, Few clouds, Partly cloudy, Partly cloudy |
|  |2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist |
|  |3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds |
|  |4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog |
|**temp** |temperature in Celsius |
|**atemp** |feeling temperature in Celsius |
|**hum** |humidity |
|**windspeed** |wind speed |
|**casual** |count of casual users |
|**registered** |count of registered users |
|**cnt** |count of total rental bikes including both casual and registered |
| --- | --- |
| --- | --- |

--------------------------------------------------------------

## Data Preparation:
--------------------------------------------------------------
- 1-	You can observe in the dataset that some of the variables like 'weathersit' and 'season' have values as 1, 2, 3, 4 which have specific labels associated with them (as can be seen in the data dictionary). These numeric values associated with the labels may indicate that there is some order to them - which is actually not the case (Check the data dictionary and think why). So, it is advisable to convert such feature values into categorical string values before proceeding with model building. Please refer the data dictionary to get a better understanding of all the independent variables.
 
- 2-	You might notice the column 'yr' with two values 0 and 1 indicating the years 2018 and 2019 respectively. At the first instinct, you might think it is a good idea to drop this column as it only has two values so it might not be a value-add to the model. But in reality, since these bike-sharing systems are slowly gaining popularity, the demand for these bikes is increasing every year proving that the column 'yr' might be a good variable for prediction. So, think twice before dropping it. 
 
--------------------------------------------------------------

## Model Building:
--------------------------------------------------------------
In the dataset provided, you will notice that there are three columns named 'casual', 'registered', and 'cnt'. The variable 'casual' indicates the number casual users who have made a rental. The variable 'registered' on the other hand shows the total number of registered users who have made a booking on a given day. Finally, the 'cnt' variable indicates the total number of bike rentals, including both casual and registered. The model should be built taking this 'cnt' as the target variable.

--------------------------------------------------------------

## Model Evaluation:
--------------------------------------------------------------
When you're done with model building and residual analysis and have made predictions on the test set. Calculate the R-Squared score on the test set to check the model performance on the unseen data.

--------------------------------------------------------------

## Methodology
--------------------------------------------------------------

- Step 1 - Reading, understanding and visualizing the data (EDA).
- Step 2 - Preparing the data for modelling (train-test split, re-scaling, etc.)
- Step 3 - Training the model
- Step 4 - Residual Analysis and Validation of Assumptions
- Step 5 - Predictions and evaluation based on the test set

--------------------------------------------------------------

## Observations from Data Visualization
--------------------------------------------------------------
- We can see a somewhat linear pattern between total number of rentals 'cnt' and temperature in deg C 'tmp'. Further we can observe that when temperature is in range of 20 to 30, number of rentals go up.
- When we observe month 'mnt' with the total number of rentals 'cnt', we observe that,
during the summer and fall months between 5 and 8 (i.e. July and September), number of rentals increases.
- When we obeserve the scatter plot of Total number of rentals to that of humidity (hum) or windspeed (windspeed), we don't observe any linear pattern here.
<br><br>
- We observe a high correlation of 0.63 when we compare count(cnt) and temperature(tmp)
- We also observe that count and humidity have a negative value of correlation. (But the strength of correlation is very less.)
- We also observe that count and windspeed have a negative value of correlation.
(Here the strength is a little higher than the above correlation)
<br><br>
- `Season`: We observe that during Fall season, the number of bikes rented are the highest followed by Summer season.
- `Month`: The highest number of rented bikes was during the month of September, followed by June and August.
- `Year`: The number of bikes rented in 2019 was higher that the number of bikes rented in 2018.
- `Holiday`: Number of bikes rented on non-holidays are higher in count and also spread wider apart as compared to bikes rented on non-holidays.
- `Weekday`: There is not much effect of this variable on the number of bikes rented, but if we were to compare, we observe that more number bikes are rented on a Thursday followed by a Sunday.
- `Workingday`: We observe that there is not much difference of bikes rented on a working day and a non-working day(Weekend).
- `Weathersit`: We can observe that a customer is more likely to rent a bike on a day with one the following weather features – 
	- a.	Clear
	- b.	Few clouds
	- c.	Partly cloudy
<br><br>

--------------------------------------------------------------------------

