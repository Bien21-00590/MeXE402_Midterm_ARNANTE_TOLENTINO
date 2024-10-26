# MeXE402_Midterm_ARNANTE_TOLENTINO
This is our Midterm Activity for Electives 2 - Machine Learning using Linear Regression and Logistic Regression for datasets about Stock Market and Iris Classification respsectively.

## **Introduction**
Overview Of Linear and Logistics Regression

**Linear regression** is a statistical method used for modeling the relationship between a dependent variable and one or more independent variables by fitting a linear equation to observed data. It's used for prediction and understanding relationships between variables. The equation for this regression is
![Screenshot 2024-10-20 082542](https://github.com/user-attachments/assets/ccee4100-8a31-4cd9-8828-c32fd4df4a4d)


Where:
- Y is the dependent variable or the output
- X1​,X2​,...Xn is the independent variable
- β0​ is the intercept 
- And β1​,β2​,...βn​ are coefficient of the independent variable

Applications for this kind of regression are predicting outcomes that are continuous(e.g., temperature, humidity,**stock prices**)



**Logistic regression** on the other hand is used for predicting the probability of a binary outcome. Unlike linear regression, which predicts continuous values, logistic regression models a binary dependent variable. The equation for this regression is
![Screenshot 2024-10-20 084038](https://github.com/user-attachments/assets/c66c5b76-c0e0-47b2-9bb5-87f9f11aa3d1)

Where:
- ln(p/1-p) is the probability outcome
- X1​,X2​,...Xn is the independent variable
- β0​ is the intercept 
- And β1​,β2​,...βn​ are coefficient of the independent variable

Applications for this kind of regression are disease prediction, yes or no output or any binary outcomes


## **Dataset Description**
### Menlo Therapeutics Stocks

This dataset is about the stock price of Menlo Therapeutics from January 25, 2018 to April 1, 2020. The **open** column is the opening stock price, the **high** column is the highest stock price of that day, the **low** column is the lowest price of that day, the **close** column is the stock price in the end of the day, the **adj close** is the adjusted value of the close value and volume is the number of shares or contracts **traded** in that timeframe.

Below is the preview of the dataset to be used in **linear regression**
![Screenshot 2024-10-20 090813](https://github.com/user-attachments/assets/ed8b1609-8424-428b-bb3b-115aa1f2e63d)



## **Objective**

The objective of the analysis of **Menlo Therapeutics Stocks** is to predict the closing value of stock price of Menlo Therapeutics and test the prediction accuracy of using linear regression based on the following parameters;
- Opening stock price of the day
- Highest/peak stock price of the day
- Low/valley stock price of the day and
- Volume of exchanges in the given timeframe



## **Linear Reggression Analysis**
### Iris Flower Classification
<img width="312" alt="overview data" src="https://github.com/user-attachments/assets/40117692-6ddd-46ea-a2e7-6c1056d09fe3">
The dataset above is about classifying three species of iris flowers based on: 
#### -Sepal Length 
#### -Sepal Width
#### -Petal Length 
#### -Petel Width

  At face value, we can observe that different species of irises can fall into a certain range of measurements on their petals and sepals however, these values can be identical and can appear again for other classifications which is why we will utilize Logistic Regression to carefully predict these outputs compared to simply using human analytical skills. This dataset has been assigned to be performed on Logistic Regression therefore its output should be a string or a classification that is not described in quantity or numerical values. 
  It is important to note that Logistic Regression is not limited to predicting only two outputs (Yes or No) which is why it is useful for machine learning in categorizing a set of parameters in this case, there must be three possible outputs for the predictions namely: Iris-setosa, Iris-versicolor, and Iris-virginica
### Data Preprocessing
  The csv file for Iris classification contains the following columns: Id, Sepal Length, Sepal Width, Petal Length, Petal Width, and Species. The Id column can be excluded for data machine learning since it only serves as a column number and has no significant impact on data prediction. This column will be later excluded in training and prediction via this line of code.
<img width="754" alt="drop" src="https://github.com/user-attachments/assets/2c03dca0-37d7-476d-9449-0bd46ca09eb2">

### Model Implementation

### Evaluation Metrics

### Interpretation


## **Logistics Reggression Analysis**


## Documentation

### Methodology

### Results

### Discussion

