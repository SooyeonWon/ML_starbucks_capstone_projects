# Starbucks Capstone Challenge
### Machine Learning Nanodegree Capstone Project
#### by Sooyeon Won

### Keywords 
- Supervised Learning
- Binary Classification Models <br>
&emsp;1. sklearn ensemble models (Random Forest, Gradient Boosting, AdaBoost) <br>
&emsp;2. XG Boost vs. Light GBM vs. CatBoost <br>
&emsp;3. Logistic Regression Model (Benchmark) <br>
- Imbalanced Data  <br>
&emsp; Synthetic Minority Oversampling Technique (SMOTE)
- Evaluation Metrics 
&emsp; Accuracy, Precison, Recall, F1-score
- Data Visualisations

### Summary of Findings

In this analysis, I analysed how Starbucks customers use offers based on the transaction data. The customer profile dataset contains a few missing data. These missing values are imputed by the median value of each features. Imputation with its own median values has several advantages. Since the median value is one of the existing values, it is realistic. Also it makes the distribution less skewed. 
By adjusting the existing features in transcript dataframe, I convert the time column into day, and month columns. <br><br>
Using the cleaned data, I explored current business situations. The number of traffics varies in each month. It increased until the third month. The change of sales amounts follows almost identical patterns with the change of traffics. We can understand that more traffics bring better sales performances. Interestingly, although the number of traffics and sales amount are different in each month, the average spending per each transaction is remarkably similar across the months. <br><br>
All customers in the profile dataset purchased products at Starbucks, although not all of them received offers. The average age of customers are 54.5 years old, and their average yearly income is around 65227. There is no significant difference between genders regarding the received type of offers. Finally, the total number of offers and the number of each type of offers are not correlated with customer's ages, incomes, the number of days as a Starbucks member. <br><br>
The number of issued offers is unbalanced. 'BOGO' and 'Discount' types of offers are almost evenly distributed; around 30000. On the other hand, "Informational" type of offer is issued only the half of them (ca. 15000). Not all of the issued offers are viewed. Only 75,68% (= 57725/76277) of offers are checked by customers. Only half of issued 'BOGO' and 'discount' offers are completed. <br><br>
In addition, I explored customer purchasing patterns based on RFM analysis. RFM is an evaluation method to analyse customer value. It is often used in database marketing especially in retail and professional services industries. RFM indicates the following 3 dimensions: Recency, Frequency, Monetary Value. <br><br>
As mentioned in Capstone proposal, I defined the desirably used offers by both Case 1 and Case 2. Based on the definition, I identified all offer usages into 2 groups: 'desirable', 'non-desirable' per each offer type. As you can see the first bar chart in the part 2, all three datasets highly imbalanced. Therefore, I alleviated the unbalanced datasets by applying Synthetic Minority Oversampling Technique (SMOTE). Then I trained each dataset with various classification models.  <br><br>
For all type of offers, "LGBMClassifier" shows one of the outstanding model performances. Also the model performed well within a shorter period of time. It achieved 0.7689, 0.7338, 0.8811 of f1-score for bogo, discount, informational datasets, respectively.  I additionally compare the input features that show significant difference between 'desirably' predicted samples and 'non-desirably' predicted samples.
At the end of the analysis, I predict the "Desirability" based on the current customers data and by applying LightGBM Classifier.   Among the customer characteristics, 'Days as Member', 'Frequency' and 'Monetary' show significant differences between "desirably"  predicted and "non-desirably"  predicted customers. Customers who are predicted as desirable users show (significantly) higher values on 'Days as Member', 'Frequency' and 'Monetary'. This indicates that customers who are predicted as desirable users are more likely to have longer memberships, to purchase more often and to spend more.

### References 
- [Gender Classification](https://de.wikipedia.org/wiki/Datenstandards_zur_Beschreibung_des_Geschlechts)<br>
- [Tidy Data](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html)<br>
- [RFM analysis](https://en.wikipedia.org/wiki/RFM_(market_research))<br>
- [Imbalanced Data 1](https://www.analyticsvidhya.com/blog/2017/03/imbalanced-data-classification/)<br>
- [Ensembling/Stacking in Python](https://www.kaggle.com/arthurtok/introduction-to-ensembling-stacking-in-python)<br>
- [Feature Selection](https://machinelearningmastery.com/feature-selection-with-real-and-categorical-data/) <br>
- [SMOTE](https://machinelearningmastery.com/smote-oversampling-for-imbalanced-classification/)<br>
- [CatBoost/ Light GBM/ XGBoost](https://towardsdatascience.com/catboost-vs-light-gbm-vs-xgboost-5f93620723db)<br>
- [CatBoost/ Light GBM/ XGBoost 2](https://towardsdatascience.com/boosting-showdown-scikit-learn-vs-xgboost-vs-lightgbm-vs-catboost-in-sentiment-classification-f7c7f46fd956)<br>
- [XGBoost](https://machinelearningmastery.com/develop-first-xgboost-model-python-scikit-learn/)<br>

