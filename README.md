# Spark_project_DSND
Spark_project_DSND

# Summary
This notebook explores features related to whether or not a customer churns for a Sparkify, a ficticious music streaming company. 


# Prerequisites
Anaconda 3 https://www.anaconda.com/distribution/
Pyspark
Scikit-Learn
Pandas
Matplotlib
Seaborn

# Files
Sparkify.ipynb - Notebook with analyses and findings. Includes loading and cleaning data, EDA, defining churn, feature engineering, and modeling.  
mini_sparkify_event_data.json - json data file


# Main findings 

## EDA findings:
- 52/225 unique users saw the cancellation confirimation page. This page can be seen by both free and paid customers.

- 49/225 users saw the submit downgrade page. This can only occur for paid users.

- 92/225 users saw the cancellation confirmation or submit downgrade page.

- We shall proceed to a user as churned if a user has seen the cancellation confirmation page.

## Churn definition findings:
- We found that users who see the cancellation confirmation page do not have any activity after this point. Because of that, we can define churned users as those who have seen the cancellation confirmation page.

- Using this definition, we can proceed to define churned users as those who have seen the cancellation confirmation page.


## Churn EDA findings:
- Aggregate stats indicate that, in general, users who churned have:

- Shorter account ages than users who didn't churn, suggesting that the longer a user has had an account, the less likely they are to churn.

- A slightly higher average for next songs per day, indicating that maybe churned users flip through more songs (and don't complete as many) as users who didn't churn.

- A slightly lower average number of thumbs up per day, suggesting that users who churn are less engaged in this manner.

- A slightly higher number of adds to playlists per day, indicating that perhaps churned users are a little more particular about their music tastes.

- A marginally higher average number of friends added per day.

- A higher average number of thumbs down per day, indicating that churned users are more active in voicing negative opinions in this manner.

- The churn by gender barplot shows that males are slightly more likely to churn than females.

- Note, the averages for next songs per day, thumbs up per day, and added friends per day are marginally different and out sample size is quite small at 225 users, so we should definitely take these findings with a grain of salt


## Modeling findings

- We see that the random forest model performs best in terms of the training f1 score and not overfitting the training data when compared to logistic regression and gradient boosted trees. To reduce processing time, I pursued cross validation with the random forest model to further optimize parameters.

- Areas for future improvement:
Note, we are performing this analysis on a subset of the data, so data points when using userId as the unit of analysis is somewhat minimal with 225 observations. This shouldn't be a problem if we were to scale the script to the full dataset.

If we wanted to create more data points with this data, one option might be to create rolling averages for each user to predict whether or not they'll churn the next day. We could do this by looking at their activity the past week and past month. If activity during the past week is different in a predictable way, that might lend itself to predicting future churn.


# Citations 
Udacity Data Science Nanodegree Program https://www.udacity.com/course/data-scientist-nanodegree--nd025

Spark Documentation https://spark.apache.org/ 
