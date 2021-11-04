# Ford Go Bike Data Exploration
## by Mostafa Hasan Mahmoud


## Dataset

The dataset containing information about individual rides made in a bike-sharing system covering the greater San Francisco Bay area from 2019-02-01 to 2019-02-28 with a total of 28 days, containing 183412 rows and 16 columns.
The dataset can be found in: 
Udacity - (https://video.udacity-data.com/topher/2020/October/5f91cf38_201902-fordgobike-tripdata/201902-fordgobike-tripdata.csv),
with feature documentation available in: 
Udacity - (https://video.udacity-data.com/topher/2019/April/5ca78b26_dataset-project-communicate-data-findings/dataset-project-communicate-data-findings.pdf)

Data wrangling steps that I performed before starting the exploration:
- Converting the (start_time, end_time) columns from object to datetime using the to_datetime() method.
- Adding day and hour columns to fgb dataframe.
- Creating a new column for the members age in 2019.
- Dropping the columns ('member_birth_year', 'start_station_latitude', 'start_station_longitude', 'end_station_latitude', 'end_station_longitude').
- Removing the null values from the fgb dataframe.
- Convert user_type, member_gender, bike_share_for_all_trip, stday_name, enday_name into ordered categorical types.
- Creating a sample of 500 rides to use it when needed so that plots are clearer and they render faster.


## Summary of Findings

In the exploration, I found that:

- The duration of trips in the data set takes a very large range of values, from 61 to 84548 s, with the maximum turning out to be 7958 s after removing outliers. The ride duration distribution takes a unimodal shape, and the beak ranges between 261 and 361 seconds.
- The breakdown of the total number of trips made each day shows that the number of trips increases from Monday to Thursday with the maximum number of trips on Thursday, while the minimum trips take place on Saturday and Sunday "weekend."
- Breaking down the total number of rides made by hour shows that the number of rides increases from 7 am to 9 pm with maximum rides at 5 pm and 8 am respectively. And minimum rides are from 0 am to 6 am.
- The highest starting stations in the total number of rides are "Market St at 10th St", "San Francisco Caltrain Station 2 (Townsend St at 4th St)", "Berry St at 4th St".
- The lowest starting stations in the total number of rides are "21st Ave at International Blvd", "Palm St at Willow St", "16th St Depot".
- Some bikes made 179 rides and others only made one. The most used bike id is from 3991 to 6638.
- 90% of rides is taken by subscribers.
- Most of the rides were observed in the age group of users between 24 and 31 years old, often the older the member, the lower the total number of rides made.
- Male users represent 75% of the total users, while female users represent 23% of the total users, while other users represent only 2% of the total users.
- Most rides are not members of bike_share_for_all_trip.
- The average ride duration of the “Customer” user type was higher than that of the “Subscriber” user type and with a higher frequency.
- Riding duration was observed to be higher for non-bike_share_for_all_trip users. And a high median for non-bike_share_for_all_trip users.
- The numbers of the Subscriber user type are much larger than the numbers of the Customer type in all stations. The highest number of Subscriber users is 3369.0 on Market Street at 10th St.
- The numbers of the Subscriber user type are much larger than the numbers of the Customer type in all stations. The highest number of Customer users is 417.0 at the San Francisco Ferry Building (Harry Bridges Plaza) station.
- The ("bike_share_for_all_trip":No) count for Subscribers is larger than Customer, and only Subscribers has ("bike_share_for_all_trip":Yes).
- Subscribers made more trips, more frequency in the duration of Subscribers’ rides, and most of the high-duration rides were made by Customers. An increase in the age groups of Subscribers from Customers.


## Key Insights for Presentation

For the presentation, I focus on the categories and times of rides that can be used to predict the rides counts. The main focus was on the following columns: duration_sec, start_station_name, end_station_name, bike_id, user_type, member_gender, bike_share_for_all_trip, stday_name, stday_num, sthour, and member_age_2019.

Afterward, I introduce each of the categorical and the numerical variables one by one using univariate visualizations, then explored the relations between them using bivariate and multivariate visualizations. 
