# **Credit Risk Prediction**

*download dataset* [here](https://rakamin-lms.s3.ap-southeast-1.amazonaws.com/vix-assets/idx-partners/loan_data_2007_2014.csv)

*presentation slide* [here](https://www.canva.com/design/DAFV1rCeUWw/ROvw4_t1EIn63n8ZedxuEA/view?utm_content=DAFV1rCeUWw&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

## **Background**

The high non performing loan (NPL) rate causes a loss for the lending company. We need a system to help reducing the non performing loan rate.

## **Objective**

Make a machine learning model that able to predict correctly that a loan will become a NPL or a good loan.

## **Requirement**
1. Numpy version: `1.21.6`
2. Pandas version: `1.3.5`
3. Matplotlib version: `3.2.2`
4. Seaborn version: `0.11.2`
5. Sklearn version: `1.0.2`

## **Dataset**

The dataset that we use for this project is **loan record dataset**. The dataset consists of **466,285 rows** and **75 columns**. The dataset and its dictionary file can be found in this repository.

## **Exploratory Data Analysis (EDA)**

Here are some inquiries during the EDA acticity.

1. Some features contains many (more than 40%) missing values. These features will be dropped.
2. Many numerical features are not normally distributed. Consider to apply log or yeo johnson transformation.
3. Some categorical features contain only single unique value, some others dominated by only single unique value. Consider to drop these features.
4. Some features have a high correlation with other features. Consider to use informational value to drop high correlated features.

## **Preprocessing**

The followings are results for each preprocessing step.
1. **Useless Features:** 30 useless features are dropped. 45 columns remaining.
2. **Feature Extracion:** Extracting values from existing features. Total of 8 features are extracted.
3. **Missing Values:** Dropping 4 features with more than 40% missing values. Replacing missing values for other features with 0 or feature's median.
4. **Feature Encoding:** Applying Weight of Evidence encoding for categorical features.
5. **Feature Selection:** Dropping features with high correlation with other features. The dropped features is the features with smaller informational value.
6. **Feature Transformation:** Yeo Johnson transformation for numerical features. Then, all features are scaled by MinMaxScaler.
7. **Imbalance Handling:** Oversampling by SMOTE method with a sampling strategy of 0.5.

## **Modeling**

For this project, I experimented with two machine learning models, namely Logistic Regression and Decision Tree Classifier. After evaluating their performance, I decided to implement the Decision Tree Classifier as it showed better results compared to Logistic Regression.

**Hyperparameters** : max_depth = 8

**Performance Scores (Test Set)**

1. Accuracy: 0.97
2. Precision: 0.83
3. Recall: 0.95
4. F1: 0.89
5. AUC: 0.99


Due to target imbalance, AUC was choosen for the main metric.


Refers to the AUC score (>85%), the trained Logistic Regression model has a good performance. The model also able to correctly predict 95% of entire non performing loans.

## **Conclusion**

The trained Decision Tree Classifier model for this project has a very good performance. The model has a AUC score of 99% that means the model can correctly predict 99% from total prediction. The model can correctly predicted about 95% of entire non performing loans.