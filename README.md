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


## **Linear Regression Analysis**
### Menlo Therapeutics Stock
![Screenshot 2024-10-20 090813](https://github.com/user-attachments/assets/8f55bb91-8ac8-4a87-8995-1409470ae1b5)

The dataset above is the Menlo Therapeutics Stock prices and number of exchanges from January 25, 2018 to April 1, 2020. The open column is the opening stock price, the high column is the highest stock price of that day, the low column is the lowest price of that day, the close column is the stock price in the end of the day, the adj close is the adjusted value of the close value and volume is the number of shares or contracts traded in that timeframe.

### Objectives

  The objective of the analysis of **Menlo Therapeutics Stocks** is to predict the closing value of the stock price of Menlo Therapeutics by using **Linear Regression**, create and train the model and test the prediction accuracy of using linear regression by computing for the **R-Squared**, **Adjusted R-Squared**, and **Mean Squared Error** based on the following parameters;
  
#### - Opening stock price of the day
#### - Highest/peak stock price of the day
#### - Low/valley stock price of the day and
#### - Volume of exchanges in the given timeframe

### Data Preprocessing
#### Cleaning The Dataset

The Figure 1.a is the overall data of stock prices of Menlo Therapeutics and the date recorded.

![Screenshot 2024-10-18 181654](https://github.com/user-attachments/assets/a471f718-564f-4230-8f24-1739546a9ee1)
(Figure 1.a)

The prediction that we are going to make is the close value of the stock price since according to Investopedia [2], Volume is an important indicator in technical analysis because it measures the relative significance of a market move. The higher the volume during a price move, the more significant the move; the lower the volume during a price move, the less significant the move. 
Based on that, moving the close column to the last to serve as the dependent variable on Figure 1.b.

![Screenshot 2024-10-18 181725](https://github.com/user-attachments/assets/2cc7d3a2-05cd-4239-815f-1d850613d0ad)
(Figure 1.b)

Taking a closer look, the adjusted close is similar to the close so a comparison test is then made on Figure 1.c. According to Groww [3], closing price simply refers to the cost of shares at the end of the day, the adjusted closing price takes dividends, stock splits, and new stock offerings.

![Screenshot 2024-10-18 181931](https://github.com/user-attachments/assets/40a75f28-38ef-4c8a-a1c7-e5f5886ee02d)
(Figure 1.c)

After verifying that the close and adjusted close are exactly the same, we simply remove the adjusted close column because it is not in our independent variable. 

![Screenshot 2024-10-18 182003](https://github.com/user-attachments/assets/ebc3f1c7-e359-4e61-8998-bba2ebcbcda1)
(Figure 1.d)

After cleaning and arranging the dataset to be used , it is now ready for coding 

![Screenshot 2024-10-18 182100](https://github.com/user-attachments/assets/3c814e91-6ffc-4c54-801d-3f88ad8fe500)
(Figure 1.e)

### Data Showcasing

![full plot](https://github.com/user-attachments/assets/616da86f-f9ed-40fc-aac1-5e7faddc1bf8)

The plot above show the linearity relationship of each independent variable to the dependent variable. Based on the plots, the volume has the worst linearity relationship to the dependent variable due to being negative exponential related instead of a positive linear relation which mean that this could be a factor that affect the prediction of the model. Additionally from observation that there are only few outlier values which in theory will not affect the model that much.


### Model Implementation



### Evaluation Metrics


### Interpretation


### Discussion of Results



## **Logistics Reggression Analysis**
### **Iris Flower Classification**
<img width="311" alt="dataset preview" src="https://github.com/user-attachments/assets/119c949b-03f2-401a-be8c-88668dde355b">

The dataset above is about classifying three species of iris flowers based on: 
#### -Sepal Length 
#### -Sepal Width
#### -Petal Length 
#### -Petal Width

  At face value, we can observe that different species of irises can fall into a certain range of measurements on their petals and sepals however, these values can be identical and can appear again for other classifications which is why we will utilize Logistic Regression to carefully predict these outputs compared to simply using human analytical skills. This dataset has been assigned to be performed on Logistic Regression therefore its output should be a string or a classification that is not described in quantity or numerical values. 


### Objectives

  It is important to note that Logistic Regression is not limited to predicting only two outputs (Yes or No) which is why it is useful for machine learning in categorizing a set of parameters in this case:
1. We must be able to predict three possible outputs namely: Iris-setosa, Iris-versicolor, and Iris-virginica
2. Create and train a model for prediction.
3. Construct a confusion matrix as well as determine its accuracy.

  
### **Data Preprocessing**

  The csv file for Iris classification contains the following columns: Id, Sepal Length, Sepal Width, Petal Length, Petal Width, and Species. The Id column can be excluded for data machine learning since it only serves as a column number and has no significant impact on data prediction. This column will be later excluded in training and prediction via this line of code.
  
<img width="754" alt="drop" src="https://github.com/user-attachments/assets/2c03dca0-37d7-476d-9449-0bd46ca09eb2">


### **Data Showcasing**

<img width="715" alt="sepal" src="https://github.com/user-attachments/assets/ed9785fe-8216-492b-a452-b70d008bed62">
<img width="716" alt="Petal" src="https://github.com/user-attachments/assets/f137755f-1ee7-4c94-962e-e705e1cdfafc">
  
  These histograms showcase the range and frequency of values for each descriptive column. Additionally, these values are obtained or created for the application of machine learning and as assigned by our instructor, Logistic Regression, therefore using the first 4 descriptive columns we must be able to predict the 5th column which is the output or 'Species' 

### Model Preparation
  In order to properly perform Logistic Regression we must let our model know which parameters are its input and which should be the output. Our input will be Sepal Length, Sepal Width, Petal Length, and Petal Width. While our output will be Iris-setosa, Iris-versicolor, and Iris-virginica
  
  <img width="755" alt="spearate" src="https://github.com/user-attachments/assets/0ff3da50-e544-4698-98c9-e5203a3fe112">
  
  Next is that we must StandardScaler, standard scaler removes the mean and scaling to unit variance. This makes the values in the data much more easier to have a correlation for the model to learn.
  
  <img width="755" alt="standard scaler" src="https://github.com/user-attachments/assets/7b823ff0-ebc0-4aaa-a1f3-8031bd633df4">

### Model Implementation
  In this section it is now time to create the model using the prepared dataset using the code shown below
  
  <img width="746" alt="creating the model" src="https://github.com/user-attachments/assets/49b88e6f-3ff6-474e-85ab-0e4c79316450">
 
  the "max_iter=200" means that this model will have 200 iterations for our Logistic Regression.
### Evaluation Metrics
 <img width="761" alt="model prediction" src="https://github.com/user-attachments/assets/6784de19-a0b0-4007-a414-36ef31a6d6f3">
  
  After successfully creating the model and making it predict, it will now be evaluated on the following parameters:
  
**precision** - measures the accuracy of positive predictions.
**recall** - measures the model’s ability to identify all relevant instances of the positive class.
**fi-score** - it is the harmonic mean of precision and recall, balancing the two metrics.
**support** - it is the number of true instances for each class in the dataset.
**accuracy** - the overall percentage of correctly classified instances out of all instances.
**macro avg** - the unweighted average of precision, recall, and F1 score across all classes.
**weighted avg** - the average of precision, recall, and F1 score across all classes, weighted by each class’s support

### Interpretation


### Discussion of Results



