# Tweets during US elections 2020
Data Engineering Capstone Project
Project Summary
In this project, I try to analyse the tweets during the US elections of 2020 which had Trump and Biden in their hashtags in order to figure out the tweet timings, location and try to make a link the tweets from which states are more and what's the percentage of population tweeting during the elections. I have gathered the datasets from Kaggle and there are two datasets one for Trump and one for Biden, and one json dataset with the population of each state. 
The project contains, 5 dimensional tables users, twitter_details, time, location, population and one 1 fact table tweets. I have used spark for my ETL needs and the results are stored in Parquet format for further analysis needs.
