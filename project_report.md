# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Julieta Rubis

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: When I first submitted predictions generated directly from the model, I realized that some predicted values were negative, which is invalid for bike counts. To fix this, I clipped all negative predictions to zero before submission to ensure all predicted counts were non-negative, aligning with the problem domain and submission requirements.

### What was the top ranked model that performed?
TODO: The top-performing model from the initial training was the WeightedEnsemble_L3 model, which combined multiple base learners into a stacked ensemble to improve prediction accuracy. This model consistently achieved the best validation root mean squared error (RMSE) and produced the most accurate predictions on the test data.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: Exploratory data analysis revealed strong patterns related to time, such as variations in bike demand by hour of the day and day of the week. Using this insight, I engineered new features extracted from the datetime column, such as hour of day, which captured temporal demand cycles more explicitly. I also converted some categorical features like season and weather into categorical data types to improve model understanding.

### How much better did your model preform after adding additional features and why do you think that is?
TODO: Adding the new features improved model performance significantly, as reflected in a lower validation RMSE and better Kaggle public score. This improvement occurred because the model could now leverage temporal patterns explicitly captured in the additional features, leading to more accurate demand predictions.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: Hyperparameter tuning led to further improvements, fine-tuning model learning rates, tree depths, and other parameters to better fit the data. The best tuned model achieved the lowest validation RMSE and the best Kaggle score, outperforming both the initial and feature-enhanced models by optimizing the balance between bias and variance.

### If you were given more time with this dataset, where do you think you would spend more time?
TODO: Given more time, I would focus on more comprehensive feature engineering, such as creating time-based categorical bins for rush hours, temperature/humidity bins, and holiday effects. I would also experiment with individual model types, deeper hyperparameter tuning with more trials, and extensive model interpretation to understand feature impacts and improve model robustness.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default|default|default|1.32199|
|add_features|default|default|default|0.54955|
|hpo|num_trials=20|scheduler=local|searcher=random|0.51185|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
TODO: Through this project, I successfully applied AutoGluon to predict bike sharing demand with increasing sophistication. Initial modeling established a baseline, and thoughtful feature engineering captured critical temporal patterns, leading to substantial performance improvements. Hyperparameter tuning further optimized model accuracy, reducing error and enhancing predictions. This iterative approach demonstrated the importance of both data understanding and model tuning in machine learning workflows. Given more time, deeper exploration of feature transformations and model types could unlock further gains.
