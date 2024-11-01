# MeXE402_Midterm_ARNANTE_TOLENTINO
This is our Midterm Activity for Electives 2 - Machine Learning using Linear Regression and Logistic Regression for datasets about Stock Market and Iris Classification respsectively.

## **Introduction**
Overview Of Linear and Logistics Regression

**Linear regression** is a statistical method used for modeling the relationship between a dependent variable and one or more independent variables by fitting a linear equation to observed data. It's used for prediction and understanding relationships between variables. The equation for this regression is
<div align="center">
<img src="https://github.com/user-attachments/assets/ccee4100-8a31-4cd9-8828-c32fd4df4a4d">
</div>

Where:
- Y is the dependent variable or the output
- X1​,X2​,...Xn is the independent variable
- β0​ is the intercept 
- And β1​,β2​,...βn​ are coefficient of the independent variable

Applications for this kind of regression are predicting outcomes that are continuous(e.g., temperature, humidity,**stock prices**)



**Logistic regression** on the other hand is used for predicting the probability of a binary outcome. Unlike linear regression, which predicts continuous values, logistic regression models a binary dependent variable. The equation for this regression is
<div align="center">
<img src="https://github.com/user-attachments/assets/c66c5b76-c0e0-47b2-9bb5-87f9f11aa3d1">
</div>

Where:
- ln(p/1-p) is the probability outcome
- X1​,X2​,...Xn is the independent variable
- β0​ is the intercept 
- And β1​,β2​,...βn​ are coefficient of the independent variable

Applications for this kind of regression are disease prediction, yes or no output or any binary outcomes


## **Linear Regression Analysis**
### **Menlo Therapeutics Stock**  
![Screenshot 2024-10-20 090813](https://github.com/user-attachments/assets/8f55bb91-8ac8-4a87-8995-1409470ae1b5)

The dataset above is the Menlo Therapeutics Stock prices and number of exchanges from January 25, 2018 to April 1, 2020. The open column is the opening stock price, the high column is the highest stock price of that day, the low column is the lowest price of that day, the close column is the stock price in the end of the day, the adj close is the adjusted value of the close value and volume is the number of shares or contracts traded in that timeframe.

### Objectives

  The objective of implementing Linear Regression model in this dataset is to:

1.  Predict the closed value of Menlo Therapeutics Stock
2.  Create and train the dataset  in Linear Regression Model
3.  Plot the difference of actual and predicted outputs
4.  Test the accuracy of the model by calculating R^2 and Means Squared Error
  
### Data Preprocessing
#### Cleaning The Dataset

The Figure 1.a is the overall data of stock prices of Menlo Therapeutics and the date recorded.

![Screenshot 2024-10-18 181654](https://github.com/user-attachments/assets/a471f718-564f-4230-8f24-1739546a9ee1)
(Figure 1.a)

The prediction that we are going to make is the close value of the stock price since according to Investopedia, Volume is an important indicator in technical analysis because it measures the relative significance of a market move. The higher the volume during a price move, the more significant the move; the lower the volume during a price move, the less significant the move. 
Based on that, moving the close column to the last to serve as the dependent variable on Figure 1.b.

![Screenshot 2024-10-18 181725](https://github.com/user-attachments/assets/2cc7d3a2-05cd-4239-815f-1d850613d0ad)
(Figure 1.b)

Taking a closer look, the adjusted close is similar to the close so a comparison test is then made on Figure 1.c. According to Groww, closing price simply refers to the cost of shares at the end of the day, the adjusted closing price takes dividends, stock splits, and new stock offerings.

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

To implement the linear regression model, we first get the test and train variables with the test variables being 20% of the whole dataset.

![image](https://github.com/user-attachments/assets/d1707446-aefb-4b0a-bf81-d321c0ebc17b)

And after that, we fit the train variables into the model created to begin prediction.

![image](https://github.com/user-attachments/assets/07ff9d45-01f1-43ce-9155-5797fc2d3cc7)
![image](https://github.com/user-attachments/assets/52ab3dcb-5238-4519-8cb9-8f1316b8e480)



### Evaluation Metrics and Interpretation
#### R-Squared & Adj R-Squared
Below is the computation for the R-Squared which results in 0.9991818280984028 and the adjusted R-Squared
<div align="center">
<img src="https://github.com/user-attachments/assets/53d9fd7e-318c-4332-aaa4-2aa8e4e68db3">
<img src="https://github.com/user-attachments/assets/d2a1c8bb-0fbf-4aa0-9396-b1ff1bbcaae2">
</div>

Based on the evaluation of metrics results, the R-Squared score of 0.999181828098402 means that the model is either very good or suspicious. The score itself is very close to one which makes it questionable but it also is in the range where we can say that the model is reliable.

#### Means Squared Error(MSE)
We also calculated the MSE to get the average squared difference of the predicted and actual outputs.
![image](https://github.com/user-attachments/assets/e6ab55fb-89d7-4b91-983a-aedcfb15e2c7)

The Means Squared Error resulted in 0.04613760646767291 means that there is very little differece in the predicted.

#### Noisy Model
Since the interpretation of the reslut in R-Squared is suspicious enought, we add noise to the dataset that way it can lower the R-Squared. The figure below is the addition of 1.5 noise level in the dataset.
<div align="center">
<img src="https://github.com/user-attachments/assets/a5c5bd79-055c-4e86-85d7-d745bdbd12cf">
</div>

After that, we trained and tested the model anew and calculate for the noised R-Squared and MSE:
<div align="center">
<img src="https://github.com/user-attachments/assets/438a8e92-d780-4169-9090-6165e928be93">
<img src="https://github.com/user-attachments/assets/3d64531f-0494-4455-8dee-6211efc98407">
</div>

Based on the result of the noised R-Squared and MSE, it now result to be a reliable model getting a score on R-Squared varying from 0.96 - 0.94 and a score of MSE of 1.7 - 3. Due to the introduction of the noise, the results varies every calculation unlike the clean dataset in whiche there are no randomness introduced.

We can also see the difference of actual and noised data against the predicted values in the figures below:

![image](https://github.com/user-attachments/assets/5038af1c-b682-40e7-ba7a-0f3e28035944)
![image](https://github.com/user-attachments/assets/16a4d985-9f7c-4d2d-9a06-2724bc0acade)

Though the predicted output may be almost similar in both plots they are different enough if you look at the codes. This makes the model even more suspicious even though it is noised, it does not change the predicted output that much.
### Discussion of Results

The linear regression model fits good in this stock price prediction as it results in a highly accurate prediction, though it may seem queationable to to the analyist who may use this but it is undeniable that the prediction power of this model in this specific dataset is very good.

Moreover, the addition of the noise in the dataset makes the result better because it is not that high but the model became more suspicious as the predicted values does not change that  much or in shorter term, the noise almost didn't affect the predicted output. While adding noise can be useful for testing model robustness or simulating real-world scenarios like this stock price prediction, it makes the dataset less reliable. If the goal is to build a model for practical use, it's generally best to work with clean, high-quality data.








## **Logistics Reggression Analysis**
### **Iris Flower Classification**
<div align="center">
<img width="600" img height="700" alt="dataset preview" src="https://github.com/user-attachments/assets/119c949b-03f2-401a-be8c-88668dde355b">
</div>

The dataset above is about classifying three species of iris flowers based on: 
#### - Sepal Length 
#### - Sepal Width
#### - Petal Length 
#### - Petal Width

  At face value, we can observe that different species of irises can fall into a certain range of measurements on their petals and sepals however, these values can be identical and can appear again for other classifications which is why we will utilize Logistic Regression to carefully predict these outputs compared to simply using human analytical skills. This dataset has been assigned to be performed on **Logistic Regression** therefore its output should be a **string** or a **classification** that is not described in quantity or numerical values. 


### Objectives

  It is important to note that Logistic Regression is **not limited** to predicting only two outputs (Yes or No) which is why it is useful for machine learning in categorizing a set of parameters in this case:
1. We must be able to predict three possible outputs namely: Iris-setosa, Iris-versicolor, and Iris-virginica
2. Create and train a model for prediction.
3. Construct a confusion matrix as well as determine its accuracy.

### **Data Preprocessing**

  The csv file for Iris classification contains the following columns: Id, Sepal Length, Sepal Width, Petal Length, Petal Width, and Species. To inspect the data without alternating with other programs that view datasets, we can use commands data.info or dataset.head or even similar commands to view datasets on vscode itself however, through this method we can only observe a shortened overview of the dataset

<img width="747" alt="display data" src="https://github.com/user-attachments/assets/f6b305ab-9e09-4e1d-ae43-fc515b6d17b4">
<img width="754" alt="display info" src="https://github.com/user-attachments/assets/d20dbd14-2a7c-4f61-b448-6b7197e06870">

### **Data Showcasing**

<img width="715" alt="histograms" src="https://github.com/user-attachments/assets/ef7e1d47-344e-4cfb-843d-eb223d8582a2">

These histograms showcase the range and frequency of values for each descriptive column. On observation, there are commonalities for each classification and some key differences on the histograms shown which hypthetically, provide variations and unpredictability when simply done through human guessing which is then done otherwise by the succeeding training model.

### Model Implementation

The figure below is all the necessary libraries, modules and class to be used in this dataset and its functions. 

![image](https://github.com/user-attachments/assets/88fa7731-9249-4782-8899-d80f3ea43f10)

To implement the linear regression model, we first get the test and train variables but this time, the test variables will be 30% of the whole dataset due to the small size of the data only being 150 sets, lowering the test variable percentage can result in unrealistic predictions.

![image](https://github.com/user-attachments/assets/84fa262f-d6d6-4bfb-b5a6-36451f278893)

After getting the test and train variables, we fit it to a standard scale to even out the importance of each variables. This standardscaler does exactly what it is called as it implements a standard for each value so that it would be more suitable and efficient for finding patterns and help train the model.
<div align="center">
<img src="https://github.com/user-attachments/assets/92a56a7c-f2e6-451d-8383-02cbed921313">
</div>

Then we are now able to fit our train variables to the logistics regression with an iteration of 1000 to find the optimal solution. More iterations can help the model improve training the model which in turn leads to mare accurate predictions. Since logistics regression on scikitlearn can already handle multinomial logistics regression, this can only mean that we don't have to do anything special anymore.

![image](https://github.com/user-attachments/assets/e25f2594-aad5-48a8-9b90-0d4ef127e16c)
![image](https://github.com/user-attachments/assets/690d855f-dbc2-4c8a-8b24-1f50a35c4137)


### Evaluation of Metrics and Interpretation

### Accuracy Score

The function accuracy score function from scikitlearn resulted to 0.93... which means that the model implemented on the iris classification is very good. These scores can be referenced from this table.
<div align="center">
<img width="435" alt="table for accuracy" src="https://github.com/user-attachments/assets/f12f0e23-ce5e-4a29-9686-c265c57c63f8">
</div>

![image](https://github.com/user-attachments/assets/a33e0092-2b66-4338-af57-b5b687ebecbc)
![image](https://github.com/user-attachments/assets/4ab5ec94-54a0-438f-8880-71499a583887)

### Visualization

#### Confusion Matrix

The figure below is the confusion matrix that we plotted and the manual computation of the accuracy score. Since the manual computation is equal to the scikitlearn function, it is safe to say that the score is reliable.

![image](https://github.com/user-attachments/assets/9dc63c44-4f14-4de6-a961-484be77d215e)

As shown on the image,  
**1st Row:**
Iris-setosa had 14 instances of being correctly predicted and 0 instances for being predicted other than its true label.  
**2nd Row:**
Iris-veriscolor had 15 instances of being correctly predicted and 0 instances for being incorrectly predicted as Iris-setosa. However, it had 1 instance of being incorrectly predicted as iris-virginica.  
**3rd Row:**
Iris-virginica had 13 instances of being correctly predicted and 0 instances for being incorrectly predicted as Iris-setosa. However, it had 2 instances of being incorrectly predicted as Iris-versicolor.  

This total number of instances, 45, is derived from the command test_size=0.3 which means that 30% of the total rows of data (150) will have a result of 45 instances. However, in some cases, even random_state can affect this instances.


![image](https://github.com/user-attachments/assets/af3cdf19-7822-4233-910a-cdd9516c9a55)
  After successfully creating the model and training it for prediction it will now be evaluated through values measured in percentages (Note: the values shown are interpreted as percentages
  
**precision** - measures the accuracy of positive predictions.  
Iris-setosa - 1.00 or 100% of the instances were predicted as Iris-setosa corretly.  
Iris-versicolor - 0.88 or 88% of instances were predicted as Iris-versicolor correctly.  
Iris-virginica - 0.93 or 93% of instances were predicted as Iris-virginica correctly.  
  
**recall** - measures the model’s ability to identify all relevant instances of the positive class.  
Iris-setosa - 1.00  or 100% of actual Iris-setosa instances were identified correctly.  
Iris-versicolor - 0.94 or 94% of actual Iris-versicolor instances were identified correctly.  
Iris-virginica - 0.87 or 87% of actual Iris-virginica instances were identified correctly.  

**fi-score** - it is the harmonic mean of precision and recall, balancing the two metrics.  
Iris-setosa - 1.00 or 100%, a perfect score  
Iris-versicolor - 0.91or 91% , pretty okay  
Iris-virginica - 0.91 or 91%, pretty okay as well  


**support** - it is simply the number of instances found within the confusion matrix which is 14,16,15 for Iris-setosa, Iris-versicolor, and Iris-virginica respectively. totaling to a number of 45 instances. This stays true for the succeding rows for Support  


**accuracy** - the overall accuracy of the model which is 0.93 or 93%  

**macro avg** - the unweighted average of precision, recall, and F1 score without including support across all classes.  

**weighted avg** - the average of precision, recall, and F1 score including support across all classes.  

  
### Discussion
   This dataset for classifying iris categories has its advantages and disadvantages for implementing machine learning via logistic regression: (1) This dataset has no missing values and each result has its accompanied complete data. (2) The output for classification can only result to three outputs and is not complicated. (3) This dataset is easy to process due its low amount of entries. As for the disadvantages we should know that machine learning improves as more entries are processed and learned by the model, however this model has very few entries (150) and has lot of room for error when implemented on real-life applications. 
   However, after tweaking the code to the programmer's best ability, we were able to find an acceptable and accurate result suitable for the dataset provided and has been a good opportunity for learning and understanding the concepts and application of logistic regression.

### Other Notes
  Although this dataset is suitable for Logistic Regression since the data is complete as they are labeled, Clustering can also be applied as it even helps process the data more efficiently since clustering can operate even without labels. As a form of unsupervised machine learning, it can find natural patterns and key differences that logistic regression may not be able to in some cases.


References:
These references were used for constructing plot diagrams and model adjustments.

https://help.indiainfoline.com/portal/en/kb/articles/what-are-open-high-low-prev-close-prices

https://www.investopedia.com/terms/v/volume.asp#:~:text=Key%20Takeaways&text=Volume%20is%20an%20important%20indicator,the%20less%20significant%20the%20move

https://groww.in/p/adjusted-closing-price 

https://www.kaggle.com/code/sulaniishara/iris-dataset-analysis-classification#Logistic-Regression

https://www.kaggle.com/code/jeffreycrawford/logistic-regression-with-iris-dataset
