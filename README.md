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
| rating(float) | rate of the recipe 0-5 |
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
 
      ### After cleaning
| Column | Description |
| ----------- | ----------- |
| minutes(int) | time to cook the recipe |
| n_steps(int) | number of steps in recipe |
| description(str) | description about the recipe |
| ingredients(str list) | ingredients for the recipe |
| n_ingredients(int) | the amount of ingredients |
| rating(float) | rate of the recipe 0-5 |
| review(str) | review about the recipe |
| avg_rating(float) | average rating after merging the data |
| calories(float) | amount of calories for the recipe |
| total_fat(float) | amount of total fat for the recipe |
| sugar(float) | amount of sugar for the recipe |
| sodium(float) | amount of sodium for the recipe |
| protein(float)| amount of protein for the recipe |
| saturated_fat(float)| amount of saturated fat for the recipe |
| carbohydrates(float)| amount of carbohydrates for the recipe |


### Univariate Analysis
For this analysis, shows the two kind of plots to see the distributions for the ingredients and the rates.
- Using plotly to show the distribution
 - Plot1: Histgram for the number of ingredients
     - It shows the frequency of the number of ingredients in the data set. 7-8 ingredients are the most.
 - Plot2: Histgram for the rating of recipes
     - It shows the frequency of the rating. Rate 5 is the most in the data set.
  
       ## show plot here
  

### Bivariate Analysis
- Scatter Plot: Rating vs Minutes shows how rating and minits to cook are related each other. Rate 4 and 5 looks like takes more time than others.

  ## show plot here

### Interesting Aggregates
 - Aggragate data
     - groupby the rate and shows average length of description and mitures to take for each rate
       - About description length, there is no specific pattern. Almost every rate has the similar length
       - About average minute, the longest minute has 1 rate and the 2nd longest minutes has 5 rate. For other rate, the average minutes are similar.
 - Pivot table
     - index is the minutes_bin and columns are the rate 0-5, and shows each average description length
       - Almost all minutes bins are the similar length of description, but 60-120min tends to have a little longer descriptions.
      

       ## show the pivot table

## Assessment of Missingness
### NMAR Analysis
- column [review] - not all people review for the recipe, regardless of how good it is (there are 57 missing)
- column [minutes_binned] - if the recipe takes more than 120min, it will be Nan (there are 24294 mmissing)

### Missingness Dependency
Because of the amount of missingness, for [minutes binned], choose two columns for each to see the dependency if the reason of missingness is NMAR or not.
- column depends on other variable: minutes (p-value is 0.0)
    - reason: If the recipe takes long hours over the set bins, it will be missing values
- column doesn't depend on other variable: rating (p-value is 1.0)
    - reason: Rating and time to take for preparation has no correlation. Rating might be strongly related to other factor. 

 
       



  



      



