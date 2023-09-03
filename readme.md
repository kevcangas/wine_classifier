### Wine Classifier

Project designed to classify wine accroding their quality.

#### Dataset

The dataset used can be found in Kaggle [(Wine Quality Dataset)](https://www.kaggle.com/datasets/yasserh/wine-quality-dataset). This dataset includes 11 features listed next:
- Fixed acidity.
- Volatile acidity.
- Citric acid.
- Residual sugar.
- Chlorides.
- Free sulfur dioxide.
- Total sulfur dioxide.
- Density.
- pH.
- Sulphates.
- Alcohol.

The output is the quality of the wine what is a number between 0 to 10. 

### Analysis

The analysis of the dataset was done inside this [notebook](./notebook.ipynb). The first stage is focused in look the distribution of data to eliminate information that is not necessary to the model implementing a frequency table and box diagram. 

Next, the second stage is focused on the balancing samples implementing a RandomOverSampler to increase the number of the classes with some samples. 

The third stage is focused on reduce the dimensionality of the dataset implementing an Principal Component Analysis (PCA).

### Model

Finally, after the data analysis, a Random Forest model is implemented to classify. The best model hyperparameters of the model found are:

```
rf = RandomForestClassifier(n_estimators=200, 
                            random_state=00000, 
                            max_depth=7, 
                            criterion="gini", 
                            max_features=4)
```

### Result

The results obtained with this model was:

    precision    recall  f1-score   support

           3       0.99      1.00      0.99       191
           4       0.86      0.94      0.90       167
           5       0.71      0.79      0.75       206
           6       0.70      0.46      0.55       191
           7       0.81      0.86      0.84       196
           8       0.93      1.00      0.97       185

    accuracy                           0.84      1136
   macro avg       0.83      0.84      0.83      1136
weighted avg       0.83      0.84      0.83      1136