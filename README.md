# JH-Practical-Machine-Learning

You can find the htlm version of the project here:
http://rpubs.com/jpmaillard/538477

For purpose of gaining space on the project report I decided to describe my approach here.

## The Model Process:

### 1. Loading the data:
First we loaded all the data into R. I used R studio version Version 1.2.5001 on a windows 10 machine. The R version used is 3.6.1.
Two variables were create: training0 that will be used to evaluate and pick a machine learning model, test to predict.

### 2. Cleaning the data:
After that all columns containing "NA" values were removed from both data set.
I decided after reviewing their type and content the 7 first variables because they did not seem pertinent for this exercise.

### 3. Spliting the data for modeling:
Now it was time to split the training0 data into a training (60%) data set to implement the models and a testing (40%) data set that will be used to predict and validate.

### 4. Define the cross-validation:
By using the trainControl() function of the caret package we defined a variable "validControl" to be the cross-validation that will be used in each model.

### 5. Implement the 3 models:
For the 3 models we first create the model via the train() function and assign it to a variable, then we used this variable to calculate the prediction on the testing data set via the predict() function. We assign this prediction to a variable. This variable is used to create the confusion Matrix by comparing the values creating by this variable and the model$classe variable values via the confusionMatrix() function. We extract the accuracy rate out the confusion matrix and assign it to a variable. The out of sample error rate is then calculate thanks to the accuracy rate and assign to a variable.

Note: all functions here used are from the caret package.

### 6. We Compare the models and choose the best one:
We create a table containing for each model the accuracy rate and the out of sample error rates.
The model with the highest accuracy rate is then picked.

### 7. We use the winning model on the test data set:
We take the best model and apply it via the predict function from the caret package on the test model that was put aside and never used during the modeling part of this project.
