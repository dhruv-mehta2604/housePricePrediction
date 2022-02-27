# housePricePrediction
Linear Regression Model for Predicting House Prices

This Kaggle dataset consists of roughly 3,000 property listings (observations), each with 79 property attributes, and our target, sale price. The goal is to use EDA, data cleaning, preprocessing and linear model to predict home prices given the features of the home. I will follow these steps to a successful submission:

1.Exploratory Data Analysis

2.Data Preprocessing

   A.Fixing Skewness and Outliers

   B.Encoding Categorical Data

   C.Imputing Missing Values
  
3.Modelling

4.Submission

## Exploratory Data Analysis

In this initial investigations on data will be performed to to develop an understanding of the data, discover patterns and spot anomalies.

By executing the code , the average sale price of a house is close to 180,000 with most of the values falling within the 130,000 to 215,000 range. Next step is to show the relationship between the columns to examine the correlations between the features and the target.

The most correlated features to sale price were the overall quality score (79%), above-ground living area (71%), garage area (64%), and number-of-car garage (62%). Next step is to plot each variable individually against SalePrice in a scatter plot to check outliers as outliers can affect the regression model by pulling the estimated regression line further away from the true population regression line.

At first glance, there are increases in living area correspond to increases in price, with few outliers.

So there are many homes with 0 for GarageArea and there are a few outliers as well!

## Data Preprocessing

In this section the data is prepared (transformed, encoded, etc) to make it suitable for a building and training machine learning model. I chose to manually remove certain extreme outliers in the dataset to produce a better fit.

There are many ways to handle NaN values, whether to fill with the mean or median, however strings cannot be averaged or median-ed. One way to fill missing values is to impute these missing values according to their probability of occuring in the dataset to avoid single-valued imputation that impacts the quality of inference and prediction.

## Modelling

I will perform a simple linear regression on the dataset to predict house prices. In order to train out the regression model, we need to first split up the data into an X list that contains the features to train on, and a y list with the target variable, in this case, the Price column.

Split the data into training and testing set using scikit-learn train_test_split function. We are using 80% of the data for training and 20% for testing, train_test_split() returns four objects:

X_train: the subset of our features used for training

X_test: the subset which will be our ‘hold-out’ set – what we’ll use to test the model

y_train: the target variable SalePrice which corresponds to X_train

y_test: the target variable SalePrice which corresponds to X_test Now we will import the linear regression class, create an object of that class, which is the linear regression model.

Then using the fit method to "fit" the model to the dataset. What this does is nothing but make the regressor "study" the data and "learn" from it.

Coefficient of determination also called as R2 score is used to evaluate the performance of a linear regression model. It is the amount of the variation in the output dependent attribute which is predictable from the input independent variable(s).

There are three primary metrics used to evaluate linear models. These are:

Mean absolute error (MAE)

Mean squared error (MSE)

R2 Score (R2S)

MAE: The easiest to understand. Represents average error.

MSE: Similar to MAE but noise is exaggerated and larger errors are "punished". It is harder to interpret than MAE as it's not in base units, however, it is generally more popular.

R2S: It is the amount of the variation in the output dependent attribute which is predictable from the input independent variable(s).

## Submission

make the final submission on kaggle

