# Model Card

Model Page: https://github.com/ppklxto/ML-Gradient-Boosting-Regressor-Optimization-Price-Estimating

Resources and Technical Documentation:

Responsible: Jose Calixto
Terms of Use: With Permission of Author

Authors: Jose Calixto

## Model Description

This project uses a Gradient Boosting Regression model to estimate the price of a carboard carton box using flexographic technology. Specifically, narrow web.

**Input:** There are 7 inputs. all are numerical.
1.Size of the carton. Units: cubic mm
2.Board thickness. Units g/m2
3.Board Cost. Units currency
4.Ink coverage. 0= none, 1 small 2=large
5.Ink Cost. Units: currency
6.Make Ready cost. currency
7.Quantity. Units: cartons


**Output:** There is only one output
1. Price: Units: currency

**Model Architecture:** 

The model used is the Sklearn Gradient Boosting Regression model. Only 2 hyperparameters were used, the learning rate and the number of estimators.

A benchmarking model was also used in order to compare the main model. The benchmarking model was a Linear Regression model also from Sklearn.

The model was trained using 85% of the data set and 15% of the data set was used to train the model.

## Performance

I measured the performance of both models in 2 different ways:

1- Measured using MAE and RMSE median between the predictions and the test sets for each model and a comparison between both models
2- Measured using model.score() which uses the R square metric:
	u = ((y_test - y_predicted) ** 2).sum()

	v = ((y_test - y_test.mean()) ** 2).sum()

	score = 1 - (u/v) 

I find out that using the model.score() method was better and more efficient.


## Limitations

The model is very limited.

It can only take 7 inputs. A manual estimate will use more than 15 variables in order to calculate an estimate.
The model only works for flexographic narrow web printing presses. 
The dataset is very old.
The dataset was collected in a very small period of time (2 years)


## Trade-offs

The Model has performance issues for cartons that are too big. Also when quantities are too small as industrial printing is not really suited for small quantities. The model also has a limitation for each of the inputs as flexo printing narrow web presses are very limited in what they can print in size and thickness.
