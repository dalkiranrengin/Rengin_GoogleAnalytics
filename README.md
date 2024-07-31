# Rengin_GoogleAnalytics
Course: [Google Data Analytics Professional Certificate](https://www.coursera.org/learn/google-data-analytics-capstone)

In this case study, I will undertake various real-world tasks typical of a junior data analyst at the fictional company Cyclistic. To address the key business questions, I will adhere to the data analysis process, including the steps: Ask, Prepare, Process, Analyze, Share, and Act.

Dataset: [Cyclistic Data](https://divvy-tripdata.s3.amazonaws.com/index.html) (accessed on 28/07/2024)

Data Visualizations: Excel

# Background
## Cyclistic
A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use the bikes to commute to work each day.

## Scenario
I am a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, my team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

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

**How do annual members and casual riders use Cyclistic bikes differently?** 

# Prepare
I will use historical [Cyclistic Data](https://divvy-tripdata.s3.amazonaws.com/index.html) to identify trends in the first five months of 2022.

The data has been made available by Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement).

# Process
BigQuery is employed to merge and clean the various datasets into a single dataset. This is necessary because Microsoft Excel, which can only handle up to 1,048,576 rows per worksheet, is inadequate for the Cyclistic dataset's 1,122,210 rows. BigQuery, with its capacity to manage large volumes of data, is essential for this task.

# Data Combining
Query: 
5 csv files are uploaded as tables in the dataset 'Google_Case'.
"combined_data" is created to store 1,122,210 rows.

# Data Exploration
Query: 

 **Explore the dataset**
1) Columns and Data Types

![<img src="IMG_LINK" width="60" height="60"/>](https://github.com/user-attachments/assets/334c0119-b088-4a0b-9a02-c28bac27047c)

2) Number of Null Values

Following columns have missing values:
![<img src="IMG_LINK" width="80" height="80"/>](https://github.com/user-attachments/assets/3c9a2a2b-9cf0-4b9d-877c-72d0d9a96060)

3) Duplicate Rides

There are no duplicate rides in the dataset.

4) Length of Ride ID's

All ride_id's contain 16 digits.

5) Type of Membership

Members are either casual or annual users.

6) Bike Types

There are 3 bike types in the dataset:
![image](https://github.com/user-attachments/assets/f17a5435-2eda-401e-8c3c-c038a6e11e79)

7) The **"started_at"** and **"ended_at"** columns display the start and end times of trips in the format YYYY-MM-DD hh:mm
UTC. A new column, **"ride_length"**, can be created to calculate the total trip duration. There are 898 trips with durations exceeding one day and 20,954 trips with durations of less than one minute or with end times earlier than start times; these should be removed.

# Data Cleaning
Query:

1) 300300 rows with missing values were deleted.
2) "ride_length", "day_of_week" and "month" columns are added to the dataset.
3) Trips with duration less than a minute and longer than a day are excluded from the analysis.

# Data Analysis and Visualization
Query: 

1) Distribution of Bike Type Usage Among Annual and Casual Users
![image](https://github.com/user-attachments/assets/4974d208-fdc4-4927-a18b-37983117dbfa)
![image](https://github.com/user-attachments/assets/b7a8ff31-a82f-4ade-ad49-c3c1ef5ec2d3)

Among both user types, the classic bike is the most frequently used, followed by the electric bike.

2) Number of Trips by Month, Week, and Hour







 

