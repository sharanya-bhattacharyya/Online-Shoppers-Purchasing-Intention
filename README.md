# Online-Shoppers-Purchasing-Intention
Capstone project to predict Online Shoppers Purchasing Intention

## Online Shoppers Purchasing Intention Prediction System
In this data set we have perform classification or clustering and predict the intention of the Online Customers Purchasing Intention. The data set was formed so that each session would belong to a different user in a 1-year period to avoid any tendency to a specific campaign, special day, user profile, or period.

![online shopping](https://github.com/sharanya-bhattacharyya/Online-Shoppers-Purchasing-Intention/issues/1#issue-699675670)

## 1. Data
uci machine learning repository is one of the best repository to get data for projects. 
* [uci machine learning repository](https://archive.ics.uci.edu/ml/index.php)

## 2. About the Data
The dataset consists of 10 numerical and 8 categorical attributes. The 'Revenue' attribute can be used as the class label.

* "Administrative", "Administrative Duration", "Informational", "Informational Duration", "Product Related" and "Product Related Duration" represent the number of different types of pages visited by the visitor in that session and total time spent in each of these page categories. The values of these features are derived from the URL information of the pages visited by the user and updated in real time when a user takes an action, e.g. moving from one page to another. 
* The "Bounce Rate", "Exit Rate" and "Page Value" features represent the metrics measured by "Google Analytics" for each page in the e-commerce site. 
* The value of "Bounce Rate" feature for a web page refers to the percentage of visitors who enter the site from that page and then leave ("bounce") without triggering any other requests to the analytics server during that session.
* The value of "Exit Rate" feature for a specific web page is calculated as for all pageviews to the page, the percentage that were the last in the session. 
* The "Page Value" feature represents the average value for a web page that a user visited before completing an e-commerce transaction. 
* The "Special Day" feature indicates the closeness of the site visiting time to a specific special day (e.g. Mother’s Day, Valentine's Day) in which the sessions are more likely to be finalized with transaction. The value of this attribute is determined by considering the dynamics of e-commerce such as the duration between the order date and delivery date. For example, for Valentina’s day, this value takes a nonzero value between February 2 and February 12, zero before and after this date unless it is close to another special day, and its maximum value of 1 on February 8. 
* The dataset also includes operating system, browser, region, traffic type, visitor type as returning or new visitor, a Boolean value indicating whether the date of the visit is weekend, and month indicatesthe month in which someone is visiting the webpage.

## 3. Data Cleaning
In the primary dataset near about 12330 rows are present which 12330 user data samples. For cleaning the data we perform few steps.

* Problem 1 :  Duplicates are an extreme case of nonrandom sampling, and they bias to our fitted model. Including them will essentially lead to the model overfitting this subset of points.

* Problem 2 : Removing the outliers from the data to make our dataset statistically more significant. But we faced some problems while removing the outliers. some variables like "Region", "Browser" etc are defined in numbers instead of names. for example browser type 1, browser type 2 till browser type 13. so if the remove outliers directly some type of browser will be removed. So we took this kind of variables and changed their data types to "object" type and after removing the outliers we changed its data type to the previous one.

[git hub link](https://github.com/sharanya-bhattacharyya/Online-Shoppers-Purchasing-Intention/blob/master/capstonetwodata%20wrangling%20(1).ipynb)

## 4. EDA
* Checking data types and description of the variables in the Dataset
* Checking Relation between variables of the Dataset.
* checking correlation between the columns of the Dataset.
* checking distribution of the data in Dataset 
* checking the data set is imbalanced or not based on classes.

![pairplot](https://github.com/sharanya-bhattacharyya/Online-Shoppers-Purchasing-Intention/issues/2#issue-699676050)

![data distribution](https://github.com/sharanya-bhattacharyya/Online-Shoppers-Purchasing-Intention/issues/3#issue-699676570)


## 5. Modeling
Because it's a classification problem we tried with RandomForestClassifier and XGBClassifier. 

### RandomForestClassifier
![randomforest](https://github.com/sharanya-bhattacharyya/Online-Shoppers-Purchasing-Intention/issues/4#issue-699676915)

### XGBoostClassifier
![XGB](https://github.com/sharanya-bhattacharyya/Online-Shoppers-Purchasing-Intention/issues/5#issue-699677368)

## 6. Model Selection

After creting the Model for and after checking with both balanced and imbalanced data for the Xgboost model we are getting a better accuracy rate which is equals to 88 percent. So we will finalize the XGBClassifier model, with classification report as

                precision    recall  f1-score   support

      New_Visitor       0.67      0.43      0.52       344
            Other       0.14      0.60      0.23        10
    Returning_Visitor       0.91      0.95      0.93      2112

         accuracy                           0.88      2466
        macro avg       0.57      0.66      0.56      2466
     weighted avg       0.88      0.88      0.87      2466
     
## 7. Future Improvements

* In future except for this i would like to implement some unsupervised learning algorithms like clustering on the data set and try to find out natural groupings.

* USE Clustering to serve as a useful data-preprocessing step to identify homogeneous groups on which to get some useful insights from the data.

## 8. Relevant Papers:
Sakar, C.O., Polat, S.O., Katircioglu, M. et al. Neural Comput & Applic (2018).
