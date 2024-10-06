# Deep Learning Challenge

## Overview of the Analysis



The purpose of this analysis was to build a predictive neural network model for Alphabet Soup to determine which organization applying for funds would benefit the most from and use as intended the funds. The variables of the data were EIN, NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT, and IS_SUCCESSFUL. These variables represented identification number, name, application type, affiliation to companies in the same industry, government category classification of the organization, intended use of Soup, organization type, active status, income bracket, special considerations for the application, asking amount, and whether the organization was successful or not. The process involved preprocessing the data, selecting the model hyperparameters, building the model, fitting the model, and evaluating the model's predictive prowess on the testing data. Furthermore, preprocessing involved dropping unnecessary columns, grouping rarer values of categorical variables into bins, and splitting the data into training and testing data. 


## Results

* **Data Preprocessing**:
<br/>    The variable which the neural network tried to predict was IS_SUCCESSFUL, and the features which it used to predict IS_SUCCESSFUL were all other variables except EIN and NAME, namely, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT. EIN and NAME were dropped, per the instructions of the assignment, because intuitively, it didn't seem like the identification number (EIN) and the name of organization would have any bearing on whether the organization was successful in achieving its goals with the funding. 



* **Compiling, Training, and Evaluating the Model:**
<br/>
The model which performed the best on the testing data was the first model I fit with approximately an accuracy of 0.727 and a loss of 0.559. In the first model, I arbitrarily chose the tanh activation function for both hidden layers and the sigmoid activation function for the output layer. Both tanh and sigmoid functions are used for neural networks that act as binary classifiers. I wasn't sure if activation functions used for binary classifiers were only supposed to be applied to the output layer solely or to the output layer and hidden layers. For the following models, I kept everything the same, except for one change per model.
<br/> For model 2, I decreased the number of buckets of APPLICATION_TYPE, as categorical variables with too many values can cause the neural network model to underestimate those categorical variables. Other categorical variables did not seem to have too many unique values, and CLASSIFICATION seemed to have a decent number of buckets. Model 2 had a testing accuracy of approximately 0.722 and a testing loss of approximately 0.568. 
<br/>For model 3, I increased the number of nodes in each hidden layer to the (number of inputs)*3 or 42*3=126 nodes as an arbitrary change. The class material indicates increasing the number of nodes increases the speed of the neural network model but not necessarily the accuracy. Model 3 had a testing accuracy of approximately 0.727 and a testing loss of approximately 0.561. 
<br/>For model 4, I arbitarily changed the activation function of the first hidden layer to the leaky ReLu function. The rectified linear unit function can be used for classification as well, and the leaky ReLu accounts for negative numbers in the data. I did not check to see if the data had any negative numbers, so I chose the leaky ReLU, but to be a responsible aspiring data analyst, I will check in the future. Model 4 had a testing accuracy of approximately 0.725 and a testing loss of approximately 0.559.
<br/>The changes for model 3 and 4 were arbitary, as the impression I got from the classes on neural networks was finding a decent model involves trial and error. 
<br/>Finally, for model 5, I implemented all the changes from models 2-4 because I reasoned that maybe multiple changes to the model might have a reinforcing behavior on one another, creating an exponential or polynomial change, instead of a linear cumulative effect. Model 5 had a testing accuracy of approximately 0.720 and a testing loss of approximately 0.567.
<br/> Unfortunately, I was not able to develop a neural network model with an accuracy of 0.75 out of the 5 models I fitted.


  

## Summary

Overall, Model 1 performed the best with an testing accuracy of approximately 0.727 and testing loss of approximately 0.559. Model 3 had a similar testing accuracy of approximately 0.727 but had a testing loss of approximately 0.561. Because Model 3 had a worse testing loss than Model 1, I chose Model 1. A different machine learning model which I could use to solve this problem is SVM because SVM is used to classify data into 1 of 2 groups. 
