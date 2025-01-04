# data_analysis
This is a project for DSC80 at UCSD



## Introduction

This project focuses on analyzing the relationship between recipe preparation time, measured in minutes, and user ratings to uncover trends in recipe popularity. Additionally, it involves developing a predictive model to estimate average recipe ratings using key nutritional factors such as calories, fat, and sugar. By integrating exploratory data analysis with predictive modeling, this project provides valuable insights into how preparation time and nutritional profiles impact user satisfaction and preferences.

### Using recipe data
**1) Import each csv file and take a look at each content for analysis**
- import raw interaction data (rows: 731927, columns: 5)
 
| Column | Description |
| ----------- | ----------- |
| user_id(int)| user id |
| recipe_id(int) | recipe id |
| date(time) | date that the recipe is reviewed (yyyy-mm-dd) |
| rating(int) | rate of the recipe 0-5 |
| review(str) | review about the recipe |


- import raw recipes data (rows: 83782, columns: 12)
 
| Column | Description |
| ----------- | ----------- |
| name(str)| recipe name |
| id(int) | recipe id |
| minutes(int) | time to cook the recipe |
| contributor_id(int) | contributor's id |
| submitted(date) | date the recipe was submitted |
| tags(str list) | Food.com tags for recipe |
| nutrition(str) | list contains each nutrition's amount |
| n_steps(int) | number of steps in recipe |
| steps(str list) | steps to take in the recipe |
| description(str) | description about the recipe |
| ingredients(str list) | ingredients for the recipe |
| n_ingredients(int) | the amount of ingredients |
 
##  Q: How rating is going to change based on the features? 📈
- The columns I need:
    - rating - this is the main
    - minumtes, n_ingredients, steps, description, review, ingredients


## Data Cleaning and Exploratory Data Analysis
### Data Cleaning
- clean data set:
    - merge both data sets with 'recipe_id' and 'id'
    - replace all nan value with 0 in rating column
    - calculate average rating as a Series and add it to the data set
    - put nutrition column's list element into each separated columns
    - drop unnecessary columns
 
      ### I need to show the dataframe here

      



