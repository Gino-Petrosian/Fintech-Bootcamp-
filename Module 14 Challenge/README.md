Machine Learning trading Algorithm 

The goal to extract signals from the market activity is one action that can be taken by many different approaches. Traditional investing methods include Technical Analysis, Fundamental Analysis, & Cyclic Investing. Similarly to their prevelance across all industries, Machine Learning techniques provide a approach that utilizes our data rich era to its advantage. Machine Learning spans back to late 1980's and since its adoption in the markets, highly sophisticated models have been built over time. These models are available for use via programming libraries like Tensorflow, Keras, and Scikit-Learn.

The choice of the Algorithm used was influenced by the decision to favor a more risk-averse approach of training the Algorithm. As a result of this approach the Logistic Model was the chosen model. For this Algorithmic Trading Model, the goal is to back test a simple trading strategy based on the percentage change in the close data of the underlying asset and apply the SMA's to 2 different Machine learning algorithms. Once fed, the models will be tested against each other to find the model with the highest accuracy score using the Confusion Matrix. 

The Data needed was the close of the underlying asset as well as the Simple Moving Average's 4 & 100 period. This describes the Average of the close relative to the previous 4 bars and 100 bars, individually. Naturally, SMA 4 is more prone to rapid changes in value as it does not weigh any close data outside of the previous 4 data point period. Similar is true of SMA 100, and how its previous data point period is 100.

Machine Learning techniques used in this model will consist of 
        Standard Scaler to prepare for Support Vector Machine
        Support Vector Machines 
        Logistic Regression

Below you will find 2 separate confusion matrixes & attached in the Returns file you will find two images that are labeled Logistic Regression and Support Vector Machine. 
These are the original results of the 2 models implemented.

Analysis: 

###################################################################
Classification report: Support Vector Machine
SMA 4 & SMA 100

                precision    recall   f1-score   support

        -1.0       0.43      0.04      0.07      1804
         1.0       0.56      0.96      0.71      2288

    accuracy                           0.55      4092
   macro avg       0.49      0.50      0.39      4092
weighted avg       0.50      0.55      0.43      4092




Classification report: Logistic Regression  
SMA 4 & SMA 100  

                precision    recall   f1-score   support

        -1.0       0.44      0.33      0.38      1804
         1.0       0.56      0.66      0.61      2288

    accuracy                           0.52      4092
   macro avg       0.50      0.50      0.49      4092
weighted avg       0.51      0.52      0.51      4092


###################################################################
///////////////////////////////////////////////////////////////////
There are several changes I am considering when observing the SMA's 
        Period Change
                4 --> 50
                100 --> 200

The result relative to this change between each model is as follows

Classification report: Support Vector Machine
SMA 50 & SMA 200

              precision    recall  f1-score   support

        -1.0       0.45      0.20      0.28      1740
         1.0       0.56      0.81      0.67      2227

    accuracy                           0.54      3967
   macro avg       0.51      0.51      0.47      3967
weighted avg       0.52      0.54      0.50      3967




Classification report: Logistic Regression
SMA 50 & 200 

              precision    recall  f1-score   support

        -1.0       0.44      0.64      0.52      1740
         1.0       0.57      0.37      0.44      2227

    accuracy                           0.49      3967
   macro avg       0.50      0.50      0.48      3967
weighted avg       0.51      0.49      0.48      3967

The images are listed under 'LR2' and 'SVM2'

I found the results here very interesting. Certainly was not the results I was expecting in such a well known pair of trading indicators 50 and 200

###################################################################
///////////////////////////////////////////////////////////////////
The next change Im interested in making is as follows
        Period Change 
                50 --> 12
                200 --> 26

The result relative to this change between each model is as follows

Classification report: Support Vector Machine
SMA 12 & SMA 26

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1828
         1.0       0.56      1.00      0.72      2324

    accuracy                           0.56      4152
   macro avg       0.28      0.50      0.36      4152
weighted avg       0.31      0.56      0.40      4152




Classification report: Logistic Regression
SMA 12 & SMA 26

              precision    recall  f1-score   support

        -1.0       0.45      0.15      0.22      1828
         1.0       0.56      0.86      0.68      2324

    accuracy                           0.55      4152
   macro avg       0.51      0.50      0.45      4152
weighted avg       0.51      0.55      0.48      4152

Images are saved under 'LR3' & 'SVM3'

 Logistic Regression experienced a similar beginning in strategy returns when comparing it to the Support Vector Machine. While Logistic Regression did not exhibit better recall than SVM, its predictability appears to have led to a more significant difference in profits following 2018 in the data. The results from the Support Vector Machine Model in this instance were very interesting and unexpected in this chosen pair. After further researching, It appears to be the case that because the windows I set in the parameters before, the data was too smooth for the Support Vector Machine to pick up the complexity.

###################################################################
///////////////////////////////////////////////////////////////////
The next change Im interested in making is as follows
        Period Change 
                12 --> 60
                26 --> 130

The result relative to this change between each model is as follows

Classification report: Support Vector Machine
SMA 60 & SMA 130

              precision    recall  f1-score   support

        -1.0       0.51      0.03      0.05      1793
         1.0       0.56      0.98      0.71      2284

    accuracy                           0.56      4077
   macro avg       0.54      0.50      0.38      4077
weighted avg       0.54      0.56      0.42      4077




Classification report: Logistic Regression
SMA 60 & SMA 130

              precision    recall  f1-score   support

        -1.0       0.44      0.59      0.50      1793
         1.0       0.56      0.41      0.47      2284

    accuracy                           0.49      4077
   macro avg       0.50      0.50      0.49      4077
weighted avg       0.50      0.49      0.48      4077

Images are saved under 'LR4' & 'SVM4'

After observing the results, Logistic Regression did not perform well at all with the larger set of windows. Interestingly, Support Vector Machine held a high recall and performed closely with the index. While Support Vector Machine had profitable periods and unprofitable periods, there certainly is something that can be derived from this that is more profitable. Logistic regression

###################################################################
///////////////////////////////////////////////////////////////////
The next change Im interested in making is as follows
        Period Change 
                60 --> 5
                130 --> 200

The result relative to this change between each model is as follows

Classification report: Support Vector Machine
SMA 5 & SMA 200

              precision    recall  f1-score   support

        -1.0       0.45      0.30      0.36      1740
         1.0       0.57      0.71      0.63      2227

    accuracy                           0.53      3967
   macro avg       0.51      0.51      0.50      3967
weighted avg       0.51      0.53      0.51      3967




Classification report: Logistic Regression
SMA 5 & SMA 200

              precision    recall  f1-score   support

        -1.0       0.45      0.53      0.49      1740
         1.0       0.58      0.51      0.54      2227

    accuracy                           0.51      3967
   macro avg       0.52      0.52      0.51      3967
weighted avg       0.52      0.51      0.52      3967

Images are saved under 'LR5' & 'SVM5'

This backtest I think was most notable in observing logistic regressions performance against this data. It appeared to predict the best return's wise but did not perform well on the classification report. A recall resulting in .51 but the most profitable back test is an interesting observation. Support Vector Machine did not perform well with this parameter set. I was expecting much better results from Support Vector Machine with this chosen parameter set.

###################################################################
///////////////////////////////////////////////////////////////////
The next change Im interested in making is as follows
        Period Change 
                60 --> 5
                130 --> 200

The result relative to this change between each model is as follows

Classification report: Support Vector Machine
SMA 5 & SMA 200

              precision    recall  f1-score   support

        -1.0       0.45      0.30      0.36      1740
         1.0       0.57      0.71      0.63      2227

    accuracy                           0.53      3967
   macro avg       0.51      0.51      0.50      3967
weighted avg       0.51      0.53      0.51      3967




Classification report: Logistic Regression
SMA 5 & SMA 200

              precision    recall  f1-score   support

        -1.0       0.45      0.53      0.49      1740
         1.0       0.58      0.51      0.54      2227

    accuracy                           0.51      3967
   macro avg       0.52      0.52      0.51      3967
weighted avg       0.52      0.51      0.52      3967

Images are saved under 'LR6' & 'SVM6'

In this final back test, I changed the training data date to 12 months. With the same paramter as SMA's 5 & 200 leading to the most profitable Logistic Regression Model I find it would be most ideal to test with greater data.

After running it with training data of 12 months, they both significantly lowered in performance. Logistic Regression was almost trading inverse to the index but at the time of the largest drop in the index, Logistic regression lead profitable predictions. I am under the impression this could be a sign of underfitting due to the large change in the training data. 
