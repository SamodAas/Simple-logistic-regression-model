## Logistic regression model for predicting 10 heart disease risk 

### Data and its cleaning

There are 4237 observations and 16 observations all related to patients health and personal data (sex, age, education).  
There are a total of 645 empty cells which are all then filled with median values.  

Sex and education get dummy variables.  
Five columns have a few of the extreme outliers dropped.  

Columns with high correlation gets dropped to avoid multicollinearity (diaBp and prevalentHyp)

### Model building

Forward and backward step-wise model building methods are chosen to build a method. It leads to only two variables being chosen in the final model.  
Due to generally low values of predictions and having in mind that the purpose of the model is to correctly predict true positives, the cut off point to identify observation as positive is decreased to 0.1.  

### Model evaluation

Coefficients:  
const          -7.0447     
age             0.0589      
sysBP           0.0169 

Odd ratios:  
const           0.000872  
age             1.060655  
sysBP           1.017033  

Metrics:  
AUC_ROC score:  0.6500343921608426  
Accuracy:       0.5  
Recall score:   0.8617886178861789  

Confusion matrix:  
![image](https://github.com/SamodAas/Simple-logistic-regression-model/assets/55328989/8ca76080-e968-452f-aa48-4a40d5f20f99)

### Conclusion
While some of the metrics of the model would indicate very imperfect predicting, considering that the model aims to identify as many true positives in particular, the model performs relatively well, being able to predict most of the true positive observations. In order to further increase recall, the cut off point could be further lowered.
