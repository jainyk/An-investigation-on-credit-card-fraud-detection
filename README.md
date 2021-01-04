# An investigation on credit card fraud detection
 This repo analyze how various machine learning algorithms perform on balance and unbalance dataset by taking examples of credit card fraud detection.
 
# INTRODUCTION
  In the past few years machine learning has played a crucial role in resolving various problems of the businesses like spam detection, recommendation, object detection etc. Fraud detection has been a painful task for the banking, medical, and commerce industry. Hackers and criminals are continuously working on new ways to find loopholes in the system as a result it is becoming more and more difficult for the companies to authenticate their transaction. According to the Fraud Benchmark Report by cyber source 83% American businesses are conducting manual reviews, and on an average basis, they review 29 % of orders manually. India is witnessing a drastic change to online transactions. It was ranked in top 5 countries with respect to credit card fraud and cases related to debit/credit card fraud have surged to 42% in 2017 according to the Hindustan Times. According to RBI data, the number of credit cards rose by a quarter upto 38 million in the last 12 months ending in May, while the number of debit cards jumped 17% to over 925 million in the same period.

# MOTIVATION
 There are many problems with manual review in credit card fraud detection like it is costly, time-consuming and lead to high false positives which means denying a normal user for the transaction completely. By analyzing machine learning algorithms in this area, my main job is to reduce human time, computation and effort. Artificial Intelligence helps machines to identify and extend the importance of patterns in place of humans by visualizing and analyzing the data on the basis of dataset provided and taking appropriate action on the basis of feature set in a short duration of time. Traditional approaches like rule based and traditional approaches have failed due to increase in data and more variation in types of transaction. Also one of the drawback is that due to high false positive rate it leads to loss of legitimate customers and high unbalance dataset is still a matter of concern and also a wide area of research in machine learning.
 
 # OBJECTIVE
 The aim of this work is to study and analyze how machine learning algorithms like
boosting and ensembling along with data balancing algorithms like smote, adasyn and
allknn perform on fraud detection problems on unbalance and balance datasets.

# DATASET DESCRIPTION
The dataset contains 284,807 transactions among which there are 492 i.e., 0.172%
transactions are fraudulent transactions. It also contains transactions made by a cardholder in 2 days in month of september 2013 This dataset is highly unbalanced. Due
to security reasons, most of the features in the dataset are transformed using principal
component analysis (PCA). V1, V2, V3,..., V28 are PCA applied features and rest features include ‘time’, ‘amount’ and ‘class’ are non-PCA applied features.

# METRICS USED
In my current progress i have used following metrices for evaluation, these parameters
are used as base parameters for evaluation:
- Accuracy = TP + TN / TP + TN + FP + FN
- Precision = TP / TP + FP
- Recall = TP / TP + FN
- F1score = 2 * precision * recall / precision + recall
- Mcc = TP * TN - FP * FN / sqrt((TP + FP) * (TP + FN) * (TN + FP) * (TN +
FN))
- Roc = Area under curve between false positive rate and true positive rate

# RESULTS

Results for test cases without using any data balancing algorithm

| Algorithms | Accuracy | Precision | Recall | F1score | Mcc | Roc  |
| :---:      | :-:       | :-:        | :-:     | :-:      | :-:  | :-:   |
|Logistic Regression|0.99899 |0.70833 |0.70103 |0.70466 |0.70417 |0.85026|
|Log Reg with minmax|0.00170 | 0.00170| 1.0 | 0.00339| 0 |0.5|
|Decision Tree|0.99913| 0.70689 |0.84536 |0.76995 |0.77261| 0.92238|
|Random Forest|0.99961 |0.92134 |0.84536 |0.88172 |0.88234| 0.92261|
|Adaboost| 0.99933 |0.82417 |0.77319| 0.79787 |0.79794 |0.88645|
|Catboost|0.99956 |0.9 |0.83505 |0.86631| 0.86670| 0.91744|
|Xgboost| 0.99961 |0.93103| 0.83505 |0.88043 |0.88154| 0.91747|
|Lightgbm|0.99590 |0.21900 |0.54639| 0.31268 |0.34426 |0.77153|


Results for test cases using smote as data balancing algorithm

| Algorithms | Accuracy | Precision | Recall | F1score | Mcc | Roc  |
| :---:      | :-:       | :-:        | :-:     | :-:      | :-:  | :-:   |
|Logistic Regression| 0.97738 |0.06816| 0.96907 |0.12737| 0.25390| 0.97323|
|Log Reg with minmax| 0.98476 |0 |0 |0 |-0.00483 |0.49322|
|Decision Tree|0.99817 |0.48022| 0.87628| 0.62043| 0.64796| 0.93733|
|Random Forest|0.99959 |0.92134| 0.87628| 0.88172| 0.88234 |0.92261|
|Adaboost| 0.98586 |0.10313 |0.94845 |0.18604 |0.31030| 0.96719|
|Catboost| 0.99943| 0.79279 |0.90721 |0.84615| 0.84780| 0.91744|
|Xgboost|  0.99961 |0.93103| 0.83505| 0.88043 |0.88154 |0.91747|
|Lightgbm| 0.99590 |0.21900 |0.54639| 0.31268 |0.34426 |0.77153|


Results for test cases using adasyn as data balancing algorithm

| Algorithms | Accuracy | Precision | Recall | F1score | Mcc | Roc  |
| :---:      | :-:       | :-:        | :-:     | :-:      | :-:  | :-:   |
Logistic Regression| 0.96550| 0.04439| 0.93814 |0.08476 |0.20004| 0.95184|
Log Reg with minmax |0.98681| 0 |0 |0 |-0.00445| 0.49424|
Decision Tree| 0.99782| 0.43005| 0.85567| 0.57241| 0.60575| 0.92686|
Random Forest |0.99957| 0.87628 |0.87628| 0.87628 |0.87607 |0.93803|
Adaboost |0.98546 |0.10054 |0.94845| 0.18181 |0.30630| 0.96699|
Catboost |0.99949 |0.81481| 0.90721| 0.85853| 0.85952| 0.95343|
Xgboost |0.99957 |0.86138| 0.89690 |0.87878 |0.87875 |0.94833|
Lightgbm |0.99884| 0.60992| 0.88659 |0.72268 |0.73484 |0.94281|


Results for test cases using allknn as data balancing algorithm

| Algorithms | Accuracy | Precision | Recall | F1score | Mcc | Roc  |
| :---:      | :-:       | :-:        | :-:     | :-:      | :-:  | :-:   |
Logistic Regression |0.99901 |0.71578| 0.70103| 0.70833| 0.70787| 0.85027|
Log Reg with minmax |0.00170 |0.00170 |1| 0.00339 |0| 0.5|
Decision Tree |0.99913| 0.69354| 0.88659 |0.77828| 0.78374| 0.942964|
Random Forest| 0.99959| 0.92045| 0.83505| 0.87567 |0.876515| 0.91746|
Adaboost |0.99919 |0.75757| 0.77319 |0.76530 |0.76494 |0.88638|
Catboost |0.99957 |0.91011 |0.83505| 0.87096 |0.87156 |0.91745|
Xgboost |0.99963 |0.92222 |0.85567 |0.88770 |0.88814 |0.92777|
Lightgbm |0.99626 |0.26033 |0.64948 |0.37168 |0.40972 |0.82316|

# CONCLUSION
The overall project discusses the problem of credit card fraud detection and how machine learning can be used to deal with it. As stated in methodology various machine learning algorithms are compared on the basis on accuracy, precision, recall, f1score, roc and mcc. During the study while comparing various metrics for various machine learning it was found that highest accuracy was observed for xgboost using allknn, highest recall was observed for logistic regression with minmaxscaler [23] using allknn, highest precision and f1-score was observed for xgboost using allknn, highest roc and mcc score was observed for logistic regression using smote. Some results were quite an anomaly when compared to others like overall minmaxscaler doesn’t improve the model performance instead it showed down tread when used with logistic regression in terms of smote and adasyn it shown negative mcc score, value of zero for precision, recall, f1score when used with smote. On further observation true positive was found to be zero for logistic regression with smote and adasyn, true negative and false negative for logistic regression with minmaxscaler and logistic regression with minmaxscaler along with allknn is found to be 0. During analysis ’V14’ is found to be the most dominating feature when smote and adasyn are used as data balancing algorithm, also both of them are oversampling method, ’V17’ is found to be the most dominating feature when no data balancing algorithm is used. Most variation was observed in case of allknn as data balancing algorithm.
