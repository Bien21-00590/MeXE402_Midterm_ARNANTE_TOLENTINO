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

![image](https://github.com/user-attachments/assets/2c2c1140-33a2-4405-a066-7e8ddb19aec4)


The plot above show the linearity relationship of each independent variable to the dependent variable. Based on the plots, the volume has the worst linearity relationship to the dependent variable due to being negative exponential related instead of a positive linear relation which mean that this could be a factor that affect the prediction of the model. Additionally from observation that there are only few outlier values which in theory will not affect the model that much.


### Model Implementation
The figure below is all the necessary libraries, modules and class to be used in this dataset and its functions. 

![Screenshot 2024-10-28 092757](https://github.com/user-attachments/assets/e06c5a34-352e-4fc5-ab76-524ef1d1c62b)

### Evaluation Metrics and Interpretation
#### R-Squared & Adj R-Squared
Below is the computation for the R-Squared which results in 0.9991818280984028 and the adjusted R-Squared

![image](https://github.com/user-attachments/assets/53d9fd7e-318c-4332-aaa4-2aa8e4e68db3)
![image](https://github.com/user-attachments/assets/d2a1c8bb-0fbf-4aa0-9396-b1ff1bbcaae2)

Based on the evaluation of metrics results, the R-Squared score of 0.999181828098402 means that the model is either very good or suspicious. The score itself is very close to one which makes it questionable but it also is in the range where we can say that the model is reliable.

#### Means Squared Error(MSE)
We also calculated the MSE to get the average squared difference of the predicted and actual outputs.
![image](https://github.com/user-attachments/assets/e6ab55fb-89d7-4b91-983a-aedcfb15e2c7)

The Means Squared Error resulted in 0.04613760646767291 means that there is very little differece in the predicted.

#### Noisy Model
Since the interpretation of the reslut in R-Squared is suspicious enought, we add noise to the dataset that way it can lower the R-Squared. The figure below is the addition of 1.5 noise level in the dataset.

![image](https://github.com/user-attachments/assets/a5c5bd79-055c-4e86-85d7-d745bdbd12cf)

After that, we trained and tested the model anew and calculate for the noised R-Squared and MSE:

![image](https://github.com/user-attachments/assets/438a8e92-d780-4169-9090-6165e928be93)
![image](https://github.com/user-attachments/assets/3d64531f-0494-4455-8dee-6211efc98407)

Based on the result of the noised R-Squared and MSE, it now result to be a reliable model getting a score on R-Squared varying from 0.96 - 0.94 and a score of MSE of 1.7 - 3. Due to the introduction of the noise, the results varies every calculation unlike the clean dataset in whiche there are no randomness introduced.

We can also see the difference of actual and noised data against the predicted values in the figures below:

![image](https://github.com/user-attachments/assets/5038af1c-b682-40e7-ba7a-0f3e28035944)
![image](https://github.com/user-attachments/assets/16a4d985-9f7c-4d2d-9a06-2724bc0acade)

Though the predicted output may be almost similar in both plots they are different enough if you look at the codes. This makes the model even more suspicious even though it is noised, it does not change the predicted output that much.
### Discussion of Results

The linear regression model fits good in this stock price prediction as it results in a highly accurate prediction, though it may seem queationable to to the analyist who may use this but it is undeniable that the prediction power of this model in this specific dataset is very good.

Moreoover, the addition of the noise in the dataset makes the result better because it is not that high but the model became more suspicious as the predicted values does not change that  muchor in shorter term, the noise almost didn't affect the predicted output. While adding noise can be useful for testing model robustness or simulating real-world scenarios like this stock price prediction, it makes the dataset less reliable. If the goal is to build a model for practical use, it's generally best to work with clean, high-quality data.

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



