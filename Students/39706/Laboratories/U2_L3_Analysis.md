1. Simple regression: Diabetes BMI
The scatter plot shows that BMI and disease progression have a relationship. When BMI increases the target also increases. However, the points are still quite spread out, so the relationship is not perfectly linear. The positive slope means that a higher standardized BMI is associated with higher predicted disease value. The model has an R ^2 of about 0.344, which means BMI explains around 34.4% of the variation in the target for these observations
2. California Housing predictor selection
For the California HOUSING predictor model. I chose MedInce , House Age , Latitude. Looking at the scatter plots, MEDInce has the clearest relationship with house value because areas with higher median income usually have more expensive houses. HouseAge does not show a very strong pattern, but the house values still change across different ages. Latitude has a more irregular pattern, which suggests that location also affects housing prices. I chose these three predictors because they represent different parts of the problem: income, age of the houses, and location. Together, they give the model more information than using only one variable. 
3. Multiple-regression comparison and diagnostics
The intercept column adds a constant value of 1 to the design matrix, allowing the model to include an intercept term instead of forcing the prediction line through zero. The largest leverage value was approximately 0.00214, found at observations 15693 and 16171. High-leverage observations matter because unusual predictor values can have a stronger influence on the fitted model.
4. Conclusion and next step
Sí, más natural puede quedar así:
4. Conclusion and next step
These models helped me understand how linear regression works by comparing the manual calculations with scikit-learn. Both methods gave the same coefficients and predictions, which showed that the calculations were correct. One limitation is that the California Housing model only used three predictors, and the residual plot still showed a clear pattern, so the model did not explain everything in the data. A good next step would be to try different combinations of predictors or include more features and see if the predictions improve and the residuals become more random.












