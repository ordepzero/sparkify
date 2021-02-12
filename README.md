## Predicting music service churn


### 1. Introduction


A company can compare its churn and growth rates to determine 
if there was overall growth or loss. While the churn rate tracks 
lost customers, the growth rate tracks new customers. If the 
growth rate is higher than the churn rate, the company experienced 
growth. When the churn rate is higher than the growth rate, 
the company experienced a loss in its customer base.

The cost of acquiring a new customer is often much higher than retaining 
an existing one. Being able to predict churn can help a company to prioritize 
retention program on customers who are most likely to churn, taking actions 
even before a churn happens
as described in [investopedia.com](https://www.investopedia.com/terms/c/churnrate.asp#:~:text=The%20churn%20rate%2C%20also%20known,within%20a%20given%20time%20period).


This is a project of Data Science Nanodegree of Udacity  and the challenger was to predict which users
could cancel the account. The database is from Sparkify plataform of music.

## 2. Steps

<ol>
	<li>Data wrangling </li>
	<li>Data cleaning </li>
	<li>Data Exploration Analysis </li>
	<li>Feature Engineering </li>
	<li>Model </li>
	<li>Evaluation </li>
	<li>Conclusion </li>
</ol>

## 3. Datasets

- **User activity dataset** from [Udacity](https://www.udacity.com/) <br>
    The dataset logs user demographic information (e.g. user name, gender, location State) and activity (e.g. song listened, event type, device used) at individual timestamps.
- A small subset (~120MB) of the full dataset was used for exploratory data analysis and pilot modeling.

## 4. What I did
   
a) Data loading 
- Load subset from JSON
- Assess missing values
- Assess duplicated rows
- Convert timestamp columns to datetime

b) Exploratory data analysis   
- Univariate analysis
- Define churn column as cancellation of service
- Compare behavior of churn vs. non-churn users in terms of:
	- Usage at different hours of the day
	- Usage at different days of a week
	- User level (free vs. paid)
	- Event types (e.g. add a friend, advertisement, thumbs up)
	- Device used (e.g. Mac, Windows)
	- Time from downgrade to churn

c) Feature engineering for machine learning
- Create features on per user basis:
	- Number of days since registration
	- Mean, min and max time per session
	- Gender of user
	- Number of sessions
	- Time and number of artists
	- Mean time of songs listened
	- How many singers have the user heard

d. Modeling
- Split training and testing sets
- Choose evaluation metrics (Accuracy)
- Random Forest Model and Neural Network
- K-fold
- Tunning parameters
- Prediction

e. Evaluation
- Evaluate model performance

## 4. Results

- Model performance on testing set:

|testing accuracy score|
|--------|
| 0.76 |

Note that the scores are reasonably well, although not subperb. One limitation is that I was not able to run the model for a long time period given my AWS tier, so only few hyperparameters were tuned. The model performance could be further improved by tuning broader ranges of hyperparameters.

- Churns relate to users who have received more advertisements, disliked songs more often than liked, and registered more recently.
- Check out my [blog post](https://ajornadacd.blogspot.com/2021/02/predicting-churned-users.html)

## 5. Libraries
- Python
- Pandas
- Seaborn
- Matplotlib
- Scikit Learn


## 6. Repository

My github is [ordepzero](https://github.com/ordepzero) and the link for the project is
[Sparkify Project](https://github.com/ordepzero/sparkify).

6.1 File structure
- `Sparkify.ipynb`: exploratory data analysis, data preprocessing, and pilot development of machine learning model on local machine using data subset.
- `mini_sparkify_event_data.json`: subset of user activity data. I can't upload the file because the size.
- `README.md`: file with all informations needed to understand the project.
- `Untitled.ipynb`: depreciated notebook.