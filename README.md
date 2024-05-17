# Module 13 Challenge: Classification
## Problem Statement
Compare the performance of two classification models, Logistic Regression and Random Forest Classifier, applied to given email data to separate legitimate emails from spam emails.

## Methodology
Data will be split into train and test datasets. Performance will be measured by comparing the accuracy score of the two models on the test data set.

## Implementation
1. Import the data into a Pandas DataFrame.
2. Divide the data into features (`X`) columns and an outcome (`y`).
3. Randomly split the data into train and test datasets.
4. Create an instance of the Logistic Regression model, fit it to the train data, generate predictions for the test data and calculate the accuracy score of the model for the test data.
5. Create an instance of the Random Forest Classifier model, fit it to the train data, generate predictions for the test data and calculate the accuracy score of the model for the test data.
6. Compare the accuracy scores of each model to determine which performs better.

## Results
1. The Random Forest Classifier model performs slightly better, with an 95.8% accuracy score for the test data, than the Logistic Regression model, with an accuracy score of 92.3% on the same test data.
2. There does not seem to be overfitting for either model, as can be seen by the closeness of the train and test accuracy scores for both models. For the Logistic Regression model the train accuracy score is 92.6% and the test accuracy score is 92.3%. For the Random Forest Classifier model the train accuracy score is 99.9% and the test accuracy score is 95.8%.
3. The dataset is fairly balanced consisting of about 60% legitimate emails and 40% spam emails. This justifies the use of the accuracy score to comopare the models. However, this score does not account for false positives and false negatives.
4. It is not entirely surprising that the Random Forest Classifier model performs slightly better for the following reasons[^1].  
    * There is only numeric data.  
    * There are 58 columns and decision tree algorithms (such as Random Forest Classifier) handle high-dimensional data better than Logistic Regression.  
    * There are 4601 rows. That should be sufficient to overcome the danger of decision trees overfitting on small datasets.  
    * Logistic Regression performs better when there is a linear relationship between features and outcome. With 57 features it is unlikely that all those features have a linear relationship to the outcome.  
    * Logistic Regression is prone to be skewed by outliers. It is unlikely that there would not be any outliers with the large number of features.

## References
[^1]: Willig, Gustav (Jan 16, 2023). *Decision Tree vs Logistic Regression*, https://gustavwillig.medium.com/decision-tree-vs-logistic-regression-1a40c58307d0#:~:text=Decision%20trees%20are%20often%20better,features%20and%20the%20target%20variable. 

