# NYC-Taxi-Trip-Duration-Prediction---AlmaBetter-Capstone-Project

Name: Debanjan Ganguly
Email: officialdeba10@gmail.com
Project Contribution:
  - Data Wrangling – Checked for null and duplicated values
  -	Plot Distribution of numeric features
  -	Plot spatial density graph to show frequent routes
  -	Univariate and Bivariate analysis against target
  -	Plot correlation matrix
  -	Feature engineering, encoding of categorical features and standard scaling after splitting
  -	Train and test model with Linear, Lasso and Ridge Regression, DecisionTreeRegressor, Random Forest and LightBGM
  -	Plotting and Evaluation of Metrics of Model

### Project Summary

    Machine learning has been of significant help as it has helped businesses in abundant ways. We will create a model which will predict taxi trip time duration. 
    Most on-demand taxi platforms require a way to know the estimated time which driver will be occupied. It is important to predict how long a driver will have his taxi occupied. If a dispatcher or system got estimates about the taxi driver's current ride time, they could better recognize which driver to allocate for each pickup request which results to be less waiting time which means less cancellation from client side and increase in profit margin, as well as customer base.
    First thing we noticed the dataset has more than 14 lakhs of data, so we’ve implemented function which will convert dtypes of pandas dataset to numpy.int format to reduce memories. We’ve also noticed the target variable has positive extreme right skewed distribution; we’ve applied log transformation to target variable. We’ve plotted graphs, done both univariate and bivariate analysis, tried to extract general overview and stories of dataset. Also, we’ve created some new fields like distance, month and day name etc. We’ve split the dataset into 3 parts, train, test and validation. Then, we’ve applied StandardScaler by sklearn to normalize the data. We’ve tried Linear, Lasso and Ridge Regression, DecisionTreeRegressor, RandomForestRegressor and LGBMRegressor. Out of these, we found best r2_score to be ~0.75 on validation dataset using lgbm model. Though the evaluation metrics on prediction is not that much accurate, but we can use some external features like rating by user, driver experience level, driver rating or traffic conditions etc., these can significantly boost our model’s performances.


### Model Evaluation Score

|index|model|best\_score_on_train|r2\_score_on_test|adjusted\_r2_on_test|mse\_on_test|rmse\_on_test|best\_params|
|---|---|---|---|---|---|---|---|
|0|linear\_regression|0\.3436202335378016|0\.32609590348604334|0\.3260724642267743|0\.41614749966840875|0\.645094953993913|\{}|
|1|lasso|0\.34721836423030894|0\.3238208263023855|0\.3237973079129788|0\.4175523993958765|0\.6461829457637183|\{'max_iter': 1000, 'alpha': 0.01}|
|2|ridge|0\.34362029201508737|0\.326095951125833|0\.32607251186822095|0\.41614747025001014|0\.6450949311923092|\{'alpha': 1}|
|3|decision\_tree|0\.4677096790780272|0\.47089331811282564|0\.4708749150955983|0\.3267325779205078|0\.5716052640769745|\{'splitter': 'best', 'criterion': 'squared_error'}|
|4|random\_forest|0\.8307350114091425|0\.7440379154050507|0\.7440290127114851|0\.15806103875181868|0\.3975689106957669|\{'bootstrap': True, 'max_features': 'auto', 'max_depth': 50, 'min_samples_leaf': 10, 'min_samples_split': 15, 'n_estimators': 50}|
|5|lightgbm|0\.891685373928821|0\.7755822991746061|0\.7755744936356557|0\.13858183317614917|0\.3722658098404273|\{'max_depth': 50, 'n_estimators': 1000, 'num_leaves': 500}|
