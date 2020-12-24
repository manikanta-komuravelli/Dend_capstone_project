Project Summary:
In this project, I try to analyse the tweets during the US elections of 2020 which had Trump and Biden in their hashtags. 
Project Scope
I try to figure out the tweet timings, and get the user details to understand which states have more tweets for each Presidential candidate. And also, bring in the population of each state to understand more about the ratio of people tweeting from each state.
Data sets (Twitter data with hashtags) are gathered from Kaggle and the population data set from dataworld. 

Exploring And Assessing Data:
I’m using Spark as my big data framework and its libraries to do my data extraction and transformation. 
Exploration and Assessment of data includes various steps from fetching the data properly, assigning proper data types for each column, dropping the duplicates, removing the null values and grouping the data together for the creation of a data model.

Defining a Data Model:

I’m trying to define a data model with 5 dimension tables and 1 fact table
1st Dimension table- User details: This table contains user details such as user_id, user_name, user_description, user_screen_name, user_followers_count.
2nd Dimension table- twitter_details: This table contains twitter information such as tweet_id, likes, retweets, tweet, tweet source.
3rd Dimension table- time_details: This table contains time details of the tweet such as tweet_time, hour, day, week, month, day of the week.
4th Dimension table- location_details: This table contains location details of the tweet such as location, latitude, longitude, state, country
5th Dimension table- population_details: This table contains population details of the US states such as  state_name, population 

Fact table- tweet details: This is the fact table which contains details such as, user_id, tweet_id, tweet, hashtag, tweet_time, tweet_location, week_of the tweet.

Modeling the Data:
After defining the data model above, I’ve used the staged data from the spark dataframe and loaded them into the corresponding tables to be used for further analysis.


Analytics on the Data in the Data Lake:
I tried to load the parqueted data from the fact table, made a join with the location table in order to count the number of tweets from each state, and then figured out a ratio of the number of people tweeted from the entire population of each state in the USA, by joining them with the population dimension table.


Scenario Questions
How you would approach the problem differently under the following scenarios:
If the data was increased by 100x.
If the dataset was increased by 100x, I would create an EMR cluster and spin up a powerful one in order to handle a 100x bigger dataset (higher number of cores and perhaps I'll also consider an optimized EMR cluster, depending on if I care more about storage or more about computing power).
If the pipelines were run on a daily basis by 7am.
If I wanted this to be a more production level pipeline that needs to be run at 7am each day, I would convert the Jupyter notebook to a python script and use Apache Airflow to schedule it for me every day at 7 AM by making my notebook use operators and hooks
If the database needed to be accessed by 100+ people. 
If the dataset needed to be accessed by 100+ more people there should not really be a problem pulling it from S3 (Since I would be moving the script to AWS EMR). However, in case the things need to be much quicker, then I might consider transferring it to the EMR HDFS database.


