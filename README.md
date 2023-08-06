# Rossman-Retail-Sales-Prediction

Rossmann operates over 3,000 drug stores in 7 European countries.Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied.


**Problem Statement**

Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied. You are provided with historical sales data for 1,115 Rossmann stores. The task is to forecast the "Sales" column for the test set. Note that some stores in the dataset were temporarily closed for refurbishment.

**About Data set**

The given dataset is a dataset from Rossmen industry who operates over 3,000 drug stores in 7 European countries, and we have to analysis the sales of the stores and what are the factores affecting the sales. in our given dataset has 1017209 rows and 18 columnn and There are some missing values and there is no duplicate values in the dataset

Dataset link : https://www.kaggle.com/competitions/rossmann-store-sales/data

**Variables Description**

* #### Id - an Id that represents a (Store, Date) duple within the test set
* #### Store - a unique Id for each store
* #### Sales - the turnover for any given day (this is what you are predicting)
* #### Customers - the number of customers on a given day
* #### Open - an indicator for whether the store was open: 0 = closed, 1 = open
* #### StateHoliday - indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
* #### SchoolHoliday - indicates if the (Store, Date) was affected by the closure of public schools
* #### StoreType - differentiates between 4 different store models: a, b, c, d
* #### Assortment - describes an assortment level: a = basic, b = extra, c = extended
* #### CompetitionDistance - distance in meters to the nearest competitor store
* #### CompetitionOpenSince[Month/Year] - gives the approximate year and month of the time the nearest competitor was opened
* #### Promo - indicates whether a store is running a promo on that day
* #### Promo2 - Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating
* #### Promo2Since[Year/Week] - describes the year and calendar week when the store started participating in Promo2
* #### PromoInterval - describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store


**Data Wrangling and Visualization**

Data wrangling, also known as data preprocessing or data cleaning, refers to the process of transforming and preparing raw data into a suitable format for analysis. It involves cleaning, organizing, and transforming data to ensure its quality, consistency, and compatibility with the analytical tasks at hand.

Data visualization is the process of representing data and information graphically to facilitate understanding, exploration, and communication of insights. It involves creating visual representations such as charts, graphs, maps, and infographics to effectively convey patterns, trends, relationships, and comparisons present in the data.


**Hypothesis Testing**

*  Normality test using Shapiro-Wilk Test : tests If data is normally distributed
*  we used Independent Sample T-test to obtained P-value this test used to compare means of two sample. we imported ttest library from scipy to perform this test.here p value is less than 0.05 so we rejected the null hypothesis so our assumptionj becomes true that average sale of 2014 is greater than last year

 **Feature Engineering & Data Pre-processing**
 * Handling Missing Values
 *  Handling Outliers
 *  Categorical Encoding
 *  Feature Manipulation
 *  Data Transformation
 *  Data Scaling


**ML Model Implementation**

We have successfully implemented a diverse range of models, **including linear regression**, **decision tree regression**, **random forest regressor**, as well as **lasso and ridge regression**. After thorough evaluation, it became evident that the random forest regressor outperformed all the other models, exhibiting the highest level of predictive accuracy.

In our pursuit of even better results, we proactively worked on enhancing our model's performance by employing advanced techniques such as hyperparameter tuning and cross-validation. These practices allowed us to fine-tune the model's parameters and ensure it generalizes well to unseen data, ultimately leading to improved accuracy in our predictions.

As we have seen above that, Random Forest Regressor is performing the best with the accuracy of 93.7% followed by Decison Tree Regressor with accuracy of 87.3% so here we are choosing Random Forest Regressor for best prediction.

![image](https://github.com/irfan7210/Rossman-Retail-Sales-Prediction/assets/113547056/6193dcb0-c3fe-4f70-8e92-a2bb04820e64)

Random Forest is a supervised learning algorithm that can be used for both classification and regression tasks. A Random Forest regressor is a specific type of Random Forest that is used for regression tasks, which involve predicting a continuous output value (such as a price or temperature) rather than a discrete class label.

The algorithm works by creating an ensemble of decision trees, where each tree is trained on a random subset of the data. The final output is then obtained by averaging the predictions of all the trees. This helps to reduce overfitting and improve the overall performance of the model.

Random Forest regressor is known to be a very powerful algorithm that can handle high-dimensional data and a large number of input features. It is also relatively easy to use and interpret. It has several parameters that can be adjusted to optimize its performance, such as the number of trees in the ensemble, the maximum depth of each tree, and the minimum number of samples required to split a node.

###**Conclusion Regarding Accuracy of ML Models**

**Linear Regression**

It gives 79% accuracy on the test data (i.e r2_score is 0.790007 for test data). And we get 81% accuracy (r2_score = 0.8155) after using the cross-validation.

**Decision Tree**
It gives 87% accuracy on the test data (i.e r2_score is 0.8720 for test data). And 88% (i.e. r2_score = 0.8843) after tunning hyperparameter.

**Random Forest Regressor**

The random forest regressiore provides 93.77% accuracy because it is gives 0.9377 r2_score.

**L1 and L2 Regularization**
Lasso gives 14% accuracy while ridge provides approximately 79% accuracy. And elastic net is worst model for this data because it gives 9% accuracy.

After hyperparameter tunning, Lasso gives 79% (approximately) accuracy.

Among the all regression models, it is clear that Random Forest Regressor is giving the best result with the accuracy of 93.6% followed by Decison Tree Regressor with accuracy of 87.2%. So, we will use the random forest regressor to predict the sales.
