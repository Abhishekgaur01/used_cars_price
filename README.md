# used_cars_price
Here we are going to predict the price of used cars using the various machine learning models.

Now using the outcomes from the jupyter file attached we are going to answer the below question:

1.	Is this a classification or regression (prediction) problem?

Ans. This is a regression (prediction) problem

2.	Which 3 machine learning models did you select? Are there any particular reasons why?

Ans. We chose multiple linear regression, k-NN (KNeighborsRegressor) and Gradient Boosting (GradientBoostingRegressor) models for this particular problem –

a)	The KNN algorithm uses 'feature similarity' to predict the values of any new data points, which seems like an appropriate way to predict.
b)	Linear regression is less of a Blackbox and easier to communicate and understand
c)	Gradient boosting because it often provides predictive accuracy that cannot be trumped. It provides several hyperparameter tuning options that make the function fit very flexible.


3.	Outline how you preprocessed the data. Be sure to discuss (i) predictor selection, (ii) dealing with NA values, (iii) dealing with categorical predictors, and (iv) scaling.

Ans. 

a)	Predictor Selection: We have removed color based on practicality, cylinders column had the same value throughout hence we removed it and Fuel_Type_Diesel since it was highly correlated with fuel_type_petrol, other predictors exists.

b)	Dealing with NA values: 
•	“Mistlamps” has very large number of NA values, the entire column should be removed. 
•	“ID” column is just an identifier
•	“Cylinders” because it has only 1 value (4.0)
•	“Removed” the rows having NA values for Price, Color, CC, Mfr_Guarantee, Airco since the number of rows having these NA values are not that large.

c)	Dealing with categorical predictors:
•	There is only one categorical variable in our set of predictors namely Fuel_Type.
•	After flagging such categorical variable, we dropped fuel_type_diesel since it was highly correlated with fuel_type_petrol.

d)	Scaling: We have used the standard scaler and converted all values into their z value to normalize the values in the dataset.

4.	For each model that you selected, which hyperparameter(s) did you change?

Ans. 

a)	In Multiple linear regression, we don’t have any hyperparameters. Hence no changes made. 
b)	In k-NN algorithm, we changed the n-neighbor’s (k) value to the optimal value of n-neighbor. We found the optimal value of n-neighbor i.e k as 19. 
c)	For the tree-based models, we checked the performance of two models, Random Forest, and Gradient Boosting. 
	For Random Forest we have changes the n-estimators and max-depth. The values are 600 and 10 respectively.
	For Gradient Boosting we have changed the n-estimators and learning-rate. The values are 60 and 0.2 respectively.

5.	What are the training and testing performances for each model?

Ans. 

a)	For linear regression: 

	For training set Root Mean Squared Error (RMSE):  1326
	For testing set Root Mean Squared Error (RMSE):  1445

b)	For k-NN regression:

	For training set Root Mean Squared Error (RMSE):  1309
	For testing set Root Mean Squared Error (RMSE):  1517


c)	For Tree Based Models:

1.	For Random Forest Regression

	For training set Root Mean Squared Error (RMSE): 669
	For testing set Root Mean Squared Error (RMSE): 1084


2.	For Gradient Boosting Regression

	For training set Root Mean Squared Error (RMSE): 803
	For testing set Root Mean Squared Error (RMSE): 1008


6.	How would you judge the fit of each of the 3 models? Why?

Ans.


a)	For linear regression, there is very small increase (119) in the RMSE from training to test. Hence, we can say there is no overfitting. 

b)	For k-NN, there is some increase (208) in the RMSE from train to test. Hence, we can say there is little overfitting.

c)	For tree-based models:

	For Random Forest Regression There is large increase (415) in the RMSE from train to test. Hence, we can say there is overfitting.
	For Gradient Boosting There is some increase (205) in the RMSE from train to test. Hence, we can say there is little overfitting.


7.	Which model would you recommend to ACB Auctions? Why?

Ans. 
	I would recommend ACB solutions to use Gradient boosting because it has the best performance when compared to the other 2 models. 
	The model which has less RMSE is a better model. 
	As we compare the RMSE values of the models, Gradient Boosting has a better performance. 
