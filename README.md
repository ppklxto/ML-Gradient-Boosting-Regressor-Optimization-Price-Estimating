# Optimization Packaging Price Estimation Project

## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
This project allows the user to estimate the price of a cardboard box using 7 inputs:
1.	Size of the blank
2.	Board thickness
3.	Board Cost
4.	Ink coverage
5.	Ink Cost
6.	Make Ready cost
7.	Quantity
The output is the predicted price for a cardboard box.
This model should only be used for cartons to be produced in a narrow web flexographic machines. 
## DATA
The data used for the training and testing of this model was obtain from a packaging company called Pharmaflex Limited, no longer existing since 1997. All protected information under GPRS legislation has been removed. The data spans from 1996 to 1997 and contains the following data:
1.	Size: this is the size of the flat blank carton
2.	Board: This is the thickness of the board used in microns
3.	Board Cost: this is the cost per tone of the board
4.	Ink: this is an estimated coverage of the ink. 0= None, 1= Medium 2= High
5.	Ink Cost: this is the cost of the litre of ink
6.	Make Ready costs: This is the cost of setting up the press for the carton
7.	Quantity: this is the quantity of cartons required to be printed
The data was curated by myself. It was cleaned and all NaN were removed in order to make the Model as simple as possible. It has 1358 rows of data.

## MODEL 
The model I am using is a Gradient Boosting Regression. I am also using a standard Linear Regression model that I use in order to benchmark my main model. Both Models are based on the content used during my studies to obtain my Professional Diploma with Imperial College, London in Machine Learning and Ai.
The Model is very basic. It takes  7 numerical inputs and returns one output. The inputs are:
1.	Box blank Size
2.	Board thickness
3.	Board Cost
4.	Ink coverage
5.	Ink Cost
6.	Make Ready cost
7.	Quantity
The Output is the estimated price
The project uses from sklearn Linear Regression and Gradient Boosting Regression

 ## HYPERPARAMETER OPTIMSATION
The main model, Gradient Boosting Regression has 2 main hyperparameters:
1-	Learning Rate: 0.95
2-	Number of estimators: 50
The hyperparameters were found manually using validation data I left outside of the data set in order  to check how good my model would respond to real life scenarios.
Another parameter that I changed was that the dataset was divided in 85% training and 15% testing. This seems to return the best results for this problem.

## RESULTS
The plot below shows the nature of the problem. Flexographic narrow web presses are limited by the size of cartons they can produce. This correlates directly with the prices they can estimate as smaller cartons usually carry a smaller price. However, some cartons can be expensive due to the finishes they use like expensive inks or varnishes. 
![image](https://github.com/user-attachments/assets/ba413606-598c-4f06-a4a3-78d10104e4d8)

My results were very much what I was expecting from the beginning. The Linear model has a poor performance. I believe this is due to the small dataset and the week correlation of the variables I used. There are many other variables in the calculation of a price, however the main point of this project was to get a quick estimate without having to use all the variables available.
The Gradient Boosting Regression model was a much better fit for my problem. This model has more hyperparameters that can be modified in order to adapt to the problem. As the dataset used was small and with weak correlations, this model uses an ensemble of weaker models to find a better solution. 
The trade off between the learning rate and the number of estimators was a little bit problematic at the beginning. However, in order to achieve the best result, I left some data for validation and tested the results while tuning the hyperparameters. It was satisfying to find out I was able to get an acceptable error in estimating the price after spending some time tunning the parameters. 

## (OPTIONAL: CONTACT DETAILS)
Email: josecalixto@btinternet.com 
