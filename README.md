# Machine Learning Comp. 2019/20 - Income Prediction
This repository contains my solution to Trinity College Dublin's CS7CS4: Machine Learning module 2019

### **Requirements**
Python 3 (Jupyter Notebook) 

### **Problem Statement**
To apply basic machine learning models on a labelled dataset to predict the target feature 'Income in EUR' on a set of unlabelled data.

### **Approach**
I started my solution by understanding the training data. I used Pandas function _describe()_ to perform statistical analysis and visualization library _seaborn_ to picturize any established patterns/shapes.




**Data Cleaning**
- [x] NULL values: I chose to fill all missing values within the dataset with Mode of the respective column, keeping in mind the training set was not huge and I could possibly lose important data.
- [x] Encoding: Categorical features were transformed using target encoding for one-hot encoding exponentially increased my data size making it extremely difficult for the models to provide best results. 
- [ ] Noise: 
- [x] Outlier Detection: I identified outliers as the 0.01 percentile data using the function _quantile_. However, my experience in this assignment show outliers as an important feature and disregarding them would excessively overfit the model.
- [x] Feature Reduction/Selection: I chose to drop 2 features namely 'Hair Color' and 'Gender' as they were of least importance and although hardly affected my RMSE score they helped speed up my model performance. 
- [ ] Scaling/Normalisation: 

**Model Selection**
- [ ] Linear Regression: This was my first model I trained my data on. I used this model on one-hot encoding and it gave me an RMS Error of ~79,000. 
- [x] Polynomial Regression: I tried polynomial regression as an attempt to optimize my performance on my linear regression model. This however did not help to provide any significant improvements.
- [ ] Random Forest: This model was the best performing model on my data when one-hot encoded. It reduced my RMSE score from 79,000 to 76,000. Later, using target encoding this model again performed well but not better than XGBoost. 
- [ ] SVM: Support Vector Machine was comparitively slower model to train and did not perform well in either of the two encoding methodologies used. 
- [x] XGBoost: This was by far the best fit model for the problem, which not only was fast to train but provided exceptional training results. This model reduced my error from 76,000 to 60,000 with target encoding.
- [ ] Decision Trees: Decision trees being a classification model did not help in the current problem.
- [ ] KNN: I believe the results for this model were skewed even after _GridSearchCV_ optimization because of the data being synthetic. 

**Optimization Strategies**
I used cross validation and grid search techniques to overcome overfitting and determining the best paramter combination for the problem in hand. I also played around with multiple models to train my dataset. Best results were obtained when I transformed my data using _PolynomialFeatures_ and training my model on those transformed features using XGBoost. 

