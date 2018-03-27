# MDAC
Marshall Data Analytics Competition (Won 1st Place)
•	Set the agenda and led team in exploring statistical models to forecast revenue of USC Hospitality
•	Extracted and cleaned data from multiple sources, transformed raw data into features based on previous EDA
•	Performed time series forecasting using Ridge Regression model and obtained 0.24 MSE in Python
•	Delivered results and recommendations to senior manager and judges in the presentation
•	Continued providing consulting and forecasting work for USC Hospitality

In this competition, the problem is predicting revenue and customer counts in 2018, month by month, venue by venue given history data of the past two years. This is a time series forecasting problem. But since statistical model predicts future values based on its own inertia. We decided to use machine learning algorithms to solve this problem.

The first step is transfering time series data into supervised learning data by adding external variables that may influence the target. In this case, we break out seansonality using three features: month, semester and # days opened in that month. We also add four features: profit center, region, dollar per person and operation hour to explain the characteristics of each profit center. In this way, we get the supervised learning data.

Before we build the model, we need to preprocess the data. First, we transfer data into log(x+1) form. From the distribution plot of original data, we can see that its range is from 0 to 700,000, and it has a significant difference with Gaussian distribution. But after transfer it into log(x+1) form, the range decrease to 0 to 14, and the distribution is more like a Gaussian distribution. Since most machine learning algorithms require a Gaussian distribution target, this step will help our model make a good prediction. * Before I tried log(x+1) method, I standardized the original data and got its distribution plot. But I didn't use this method. Since I used the standardized data to train the model, the results of test data were also scaled. If I want to rescale the results to original form, I'll get negative value. However, you will never get negative revenue or customer counts in real life.
 
I also use One-hot Encoding to convert categorical variables into dummy variables and compute correlation matrix, drop features which are highly correlated with each other.

After we've done all of the data cleansing and preprocessing work, we can choose a machine learning model to use. Here, we use ridge regression. Ridge regression is a simple machine learning model. The difference between linear regression and ridge regression is the objective function of ridge regression has a l2 regularization term to prevent overfitting.

In general, machine learning is a method of modeling as valid as statistical model, and it always achieve better accuray in prediction.

In this competition, I did data cleaning, feature engineering, model choosing and building work. Final_model_Manqi-Ver4.ipynb is the fianl version that I used in the competition.
