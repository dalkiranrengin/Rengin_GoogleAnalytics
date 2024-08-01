# Rengin_Google_Analytics_Certificate
Course: [Google Data Analytics Professional Certificate](https://www.coursera.org/learn/google-data-analytics-capstone)

In this case study, I will undertake various real-world tasks typical of a junior data analyst at the fictional company Cyclistic. To address the key business questions, I will adhere to the data analysis process, including the steps: Ask, Prepare, Process, Analyze, Share, and Act.

Dataset: [Cyclistic Data](https://divvy-tripdata.s3.amazonaws.com/index.html) (accessed on 22/07/2024)

Data Visualizations: Excel

# Background
## Cyclistic
A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use the bikes to commute to work each day.

## Scenario
I am a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, my team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve my recommendations, so they must be backed up with compelling data insights and professional data visualizations.

A team of data analysts are responsible for collecting, analyzing, and reporting data that helps guide Cyclistic marketing strategy. I joined this team six months ago and have been busy learning about Cyclistic’s mission and business goals—as well as how you, as a junior data analyst, can help Cyclistic achieve them.

# Ask
## My Task
Provide marketing strategies to convert casual users to annual users.

## Questions
Three questions will guide the future marketing program:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

I am assigned to the first question:

**"How do annual members and casual riders use Cyclistic bikes differently?"** 

# Prepare
I will use historical [Cyclistic Data](https://divvy-tripdata.s3.amazonaws.com/index.html) to identify trends in the first five months of 2022.

The data has been made available by Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement).

# Process
BigQuery is employed to merge and clean the various datasets into a single dataset. This is necessary because Microsoft Excel, which can only handle up to 1,048,576 rows per worksheet, is inadequate for the Cyclistic dataset's 1,122,210 rows. BigQuery, with its capacity to manage large volumes of data, is essential for this task.

# Data Combining

Query: [Data Combining](https://github.com/dalkiranrengin/Rengin_GoogleAnalytics/blob/main/Data%20Combining) 

5 CSV files are uploaded as tables in the dataset **'Google_Case'**.

**"combined_data"** is created to store 1,122,210 rows.

# Data Exploration

Query: [Data Exploration](https://github.com/dalkiranrengin/Rengin_GoogleAnalytics/blob/main/Data%20Exploration)

## Explore the dataset
## 1) Columns and Data Types

![image](https://github.com/user-attachments/assets/e825dbd8-1eda-453e-9b82-6b5181d20721)


## 2) Number of Null Values

**Following columns have missing values:**

start_station_name: 204036
start_station_id: 204036
end_station_name: 218225
end_lat: 890
end_lng: 890
end_station_id: 218225

## 3) Duplicate Rides

There are no duplicate rides in the dataset.

## 4) Length of Ride ID's

All ride_id's contain 16 digits.

## 5) Type of Membership

Members are either casual or annual users.

## 6) Bike Types

There are 3 bike types in the dataset:
![image](https://github.com/user-attachments/assets/f17a5435-2eda-401e-8c3c-c038a6e11e79)

Note: The **"started_at"** and **"ended_at"** columns display the start and end times of trips in the format YYYY-MM-DD hh:mm UTC. A new column, **"ride_length"**, can be created to calculate the total trip duration. There are 898 trips with durations exceeding one day and 20,954 trips with durations of less than one minute or with end times earlier than start times; these should be removed.

# Data Cleaning

Query: [Data Cleaning](https://github.com/dalkiranrengin/Rengin_GoogleAnalytics/blob/main/Data%20Cleaning)

1) 300300 rows with missing values were deleted.
2) **"ride_length"**, **"day_of_week"**, and **"month"** columns are added to the dataset.
3) Trips with duration less than a minute and longer than a day are excluded from the analysis.
4) Cleaned data is stored in another table **"cleaned_combined_data"**.

# Data Analysis and Visualization

Query: [Data Analysis](https://github.com/dalkiranrengin/Rengin_GoogleAnalytics/blob/main/Data%20Analysis)

## 1) Distribution of Bike Type Usage Among Annual and Casual Users
![image](https://github.com/user-attachments/assets/4974d208-fdc4-4927-a18b-37983117dbfa)
![image](https://github.com/user-attachments/assets/b7a8ff31-a82f-4ade-ad49-c3c1ef5ec2d3)

**Among both user types, the classic bike is the most frequently used, followed by the electric bike.**

## 2) Number of Trips by Month, Week, and Hour

### Number of Trips Per Month
![image](https://github.com/user-attachments/assets/fbbac672-e64b-4bee-9aa1-f5bf90df8a76)

**Although both user groups exhibit similar trends in bike usage, annual members are three times more likely to use bikes compared to casual members. Additionally, bike usage peaks in April.**

### Number of Trips Per Week
![image](https://github.com/user-attachments/assets/ef3c3882-386c-403c-ab44-fc98f177ced3)

**Annual members are more likely to use bikes during weekdays, suggesting they rely on them for daily commuting, whereas casual members tend to ride bikes more often on weekends, likely for recreational purposes.**

### Number of Trips Per Hour
![image](https://github.com/user-attachments/assets/8d161690-1f07-402e-8b0f-807c365c400d)

**Both casual and annual members are more likely to use bikes between 4 AM and 6 PM, with annual members averaging three times more usage during this period. Bike usage peaks for both groups at 5 PM.**

## 3) Average Ride Lengths by Month, Week, and Hour

### Average Ride Length by Month
![image](https://github.com/user-attachments/assets/1813d9d8-0e99-4dcf-89fc-2da2cabb5ea1)

**Despite both groups exhibiting similar patterns in average ride duration from January to May, casual members utilize bikes 2.5 times longer than annual members, which supports the argument that casual users use bikes more for recreational purposes. Furthermore, while bike usage among casual members peaks in March, annual members experience their peak usage in April.**

### Average Ride Length by Week
![image](https://github.com/user-attachments/assets/e0a65956-43f2-48dd-988a-6685e53bf6a6)

**Consistent with the aforementioned graphs, casual members, on average, use bikes for twice as long as annual users.**

### Average Ride Length by Hour
![image](https://github.com/user-attachments/assets/02d8fdc8-ee9c-4a85-84f2-03310af7c058)

**While casual members exhibit a stable pattern in bike usage throughout the day, annual members show a peak in usage between 3 AM and 7 AM.**

## Conclusion

1) Casual members tend to use bikes throughout the day, with a marked preference for weekends for recreational purposes. Conversely, annual members predominantly ride bikes on weekdays during peak commute hours (8 AM and 5 PM). 

2) While casual members undertake rides that are twice as long on average, they do so less frequently. Annual members, on the other hand, ride more often but for shorter durations, roughly half the length of the rides taken by casual users.

# Act

Following strategies are recommended to convert casual members into annual members:

1) Casual riders tend to use bikes for longer durations compared to annual members. Introducing discounts for extended ride times could serve as an incentive for casual riders and encourage annual members to extend their ride durations.

2) Casual riders exhibit peak activity on weekend, suggesting the potential benefit of offering weekend-only memberships tailored to their usage patterns.













 

