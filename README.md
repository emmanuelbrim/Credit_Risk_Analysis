# Credit_Risk_Analysis
## Overview of the Project
Reducing the tendency to issuing bad loans or avoiding approval of potential defaulters is a task that loan financial setups have to deal with always.
Machine_learning helps financial institutions minimize credit risk.
The purpose of this project was to find the best machine-learning model that will help LendingClub, a peer-to-peer lending services company to reduce their credit risk by using the best machine-learning model.
Resources for the project includes;
- Google collab
- Jupyter notebook
- scikit-learn
- imbalanced-learn

## Results
The original credit dataset(LoanStats_2019Q1.csv) from peer-to-peer lending was read-in and cleaned using pandas library in jupyter notebook.
After identifying the features and target as X and y, scikit_learn's model_selection was used to split the data into training and testing variables.
A value_count on the target showed an imbalance in the sample size and therefore had to be fixed to produce the best learning model for our credit check.

![](https://github.com/emmanuelbrim/Credit_Risk_Analysis/blob/main/Resources/imbalance.PNG)

- Random Oversampling
The RandomOverSampler from imbalance-learn's over_sampling library was the first tool to be used to correct the sample imbalance.
Then scikit-learn's LogisticRegression used after to train the model suing the resampled X and y values. 

The accuracy score using this model was 0.64 and precision and sensitivity was 0.99 and 67 respectively.

Below is the results.
![](https://github.com/emmanuelbrim/Credit_Risk_Analysis/blob/main/Resources/ROS.PNG)

- SMOTE Oversampling
The Synthetic Minority oversampling technique was also used to resample the X and y values to see if it could improve the results from the LogisticRegression model.

The results showed a slight drop in accuracy but the precision and recall remained same.

The image below shows the results from SMOTE.
![](https://github.com/emmanuelbrim/Credit_Risk_Analysis/blob/main/Resources/SMOTE.PNG)

- ClusterCentroids Undersampling
From imbalance-learn's under_sampling library, the third resampling technique; clusterCentroid was used to reshape the samples from the train and test variables.
Using this model produced an improvement in accuracy over that of the SMOTE but the classification report indicated that precision and recall was same as previous model.

![](https://github.com/emmanuelbrim/Credit_Risk_Analysis/blob/main/Resources/CC.PNG)

- Combination (SMOTEENN) Sampling
A combination technique was applied to reshape the samples again. From imbalance-learn's combination library SMOTEEN was used.
Using both over and under sampling technique didnot show any improvement in accuracy and precision from previous model. 
However the sensitivity was reduced to a 0.60

![](https://github.com/emmanuelbrim/Credit_Risk_Analysis/blob/main/Resources/combination.PNG)

- Balanced Random Forest Classifier
The results from the Logistic Regression model after several resampling techniques showed improvements in the results of the fit capabilities of the model.
However inorder to see if this could be enhanced involved the use of the Random Forest classifier from imbalance-learn's ensemble library.
Th results showed a better accuracy than the other models. Accuracy score was 0.79 a leap from the 0.64 which was recorded as the highest from the previous models.
Precision and recall also showed good gains.

And the results is showed in the image below. 
![](https://github.com/emmanuelbrim/Credit_Risk_Analysis/blob/main/Resources/RFC.PNG)

- Easy Ensemble AdaBoost Classifier
The final model to be used was the AdaBoost classifier. 
The results from this model showed all metrics above 0.90. Precision remain same as other models but a huge increase in both accuracy and recall.

![](https://github.com/emmanuelbrim/Credit_Risk_Analysis/blob/main/Resources/ADB.PNG)


## Summary
A good machine learning model is one that has a good accuracy score. Accuracy is measured from 0 to 1 and a good accuracy score should be that closest to 1.
The testing of the various models show cummlative improvenments after fixing the sample size using the various techniques. 
For this project the analysis show that the AdaBoost classifier produced the best learning model. 
With an accuracy score of 0.93 it showed huge improvement from the other models.
AdaBoost classifier also produced the highest sensitivity results than all the other models.
However the precision results show that all models stood at avg/total of 0.99 reliability. 
From this its clear that the AdaBoost model is the best to be considered by perr-to-peer lending in accesing the credit worthiness of their loan applicants.
