# machine-learning-challenge

Model 1 - Random Forest 

•	The model performed well with a score of 98% on the test data
•	Feature selection was done using recursive feature elimination with cross validation (RFECV)
•	Hyper parameters were optimized using grid search
•	For both REFCV and grid search, cross validation was set to default of 5 folds 
•	REFC was nested inside grid search, this proved to be computationally intensive and both RECV and grid search did not significantly improve the performance of the model in the test data even with both functions using cross validation 
•	Trees in the forest did not have a maxim depth set as such can be prone to over fitting but given the nested cross validation in feature selection and hyper parameter selection and further since by default Sklearn has bootstrap cross validation to build each tree in the forest we can be certain model is not overfit 
•	The model is sufficient for our needs and have high confidence in its performance, however if the goal of the model is to limit manual verifications of exoplanets then we can seek to marginally improve performance by exploring models that reduce false positives, this model has a false positive rate of 4% in the test data     

Model 2 – SVM

•	Given the computational intensity of nesting RFECV with grid search and since feature elimination did not improve performance in the Random Forest model, feature elimination was skipped in this model development, however in retrospect it could have made sense to use the features chosen by REFCV in the Random Forest model as input features for the SVM model    
•	Model performed well with the score of 99% for the test data 
•	Fairy confident the model is not overfit as model was cross validated with various values of regularization value “C” via grid search, although since this model was not computational intensive cross validated during grid search could have been increased form the default 5 folds to further reduce the likelihood of overfitting 

Conclusion: both models have good performance and are not overfit, since we are solving for a binary classification problem, it makes sense to use both models in conjunction to classify exoplanets. Further analysis can be down to see if the errors in both models are consistent (i.e. both models are wrong at the same time or vise-versa) or divergent to solve for how to best use the models together to reduce false positives and thus reduce manual verification of exoplanet candidates. 
