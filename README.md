# Bitcoin Project

This project aims to predict the future price of bitcoin based on its historical data and some features derived from it. The project uses Python and several libraries such as numpy, pandas, matplotlib, seaborn, and sklearn.

## Data

The data used for this project is the bitcoin.csv file, which contains the daily data of bitcoin from 2012 to 2021. The data has 10 columns: Date, Open, High, Low, Close, Volume, Market Cap, year, month, and day.

The data is loaded and explored using pandas and matplotlib. The summary statistics and the information of the data are printed. The missing values are counted. The close price of bitcoin over time is plotted. The distribution of the open, high, low, and close prices are shown using seaborn.

## Feature Engineering

The data is enhanced by adding some new features that may have some predictive power. The features are:

- is_quarter_end: A binary variable that indicates whether the date is the end of a quarter or not.
- open-close: The difference between the open and close prices of the day.
- low-high: The difference between the low and high prices of the day.
- target: A binary variable that indicates whether the close price of the next day is higher than the current day or not.

The target variable is the label that the models will try to predict. The pie chart of the target variable shows that the data is slightly imbalanced, with more positive cases than negative ones.

## Preprocessing

The data is split into features (X) and target (y) variables. The features are the open-close, low-high, and is_quarter_end columns. The target is the target column.

The features are normalized by using a StandardScaler, which standardizes the data by removing the mean and scaling to unit variance. The data is then split into training and testing sets, with 85% of the data for training and 15% for testing. The random_state parameter is set to 2022 to ensure reproducibility of the results.

## Model

The models used for this project are four different classifiers: Logistic Regression, Decision Tree, K-Nearest Neighbors, and Support Vector Machine. These models are imported from the sklearn module and instantiated with the default parameters. The max_iter parameter is set to 10000 for the Logistic Regression model to avoid convergence warnings.

The models are fitted on the training data and used to make predictions on the testing data. The accuracy of the models is evaluated by using the ROC AUC score, which measures the ability of the models to discriminate between the positive and negative classes. The ROC AUC scores for the training and testing sets are printed for each model.

## Results

The results of the models are as follows:

- Logistic Regression: The ROC AUC score on the training set is 0.54 and on the test set is 0.53.
- Decision Tree: The ROC AUC score on the training set is 1.00 and on the test set is 0.50.
- K-Nearest Neighbors: The ROC AUC score on the training set is 0.69 and on the test set is 0.51.
- Support Vector Machine: The ROC AUC score on the training set is 0.55 and on the test set is 0.53.

The best model for this project is the Support Vector Machine, which achieved a slightly higher ROC AUC score on the test set than the other models. The worst model is the Decision Tree, which had a very low ROC AUC score on the test set and was overfitting the training data. The Logistic Regression and the K-Nearest Neighbors models had similar ROC AUC scores, but they were not very good at predicting the future price of bitcoin.
