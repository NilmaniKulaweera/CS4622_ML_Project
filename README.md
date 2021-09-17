#### GitHub Link = 

## Preprocessing and feature engineering techniques used

1. Imputed missing values in below columns using various imputation techniques

* funder - missing category imputation
* installer - missing category imputation
* public_meeting - random sample imputation
* scheme_management - constant value imputer (Company)
* scheme_name - missing category imputation
* permit - missing indicator (since not missing at random)
* subvillage - random sample imputation

2. Created the following new features

* polar =  sqrt(longitude^2 + latitude^2)
* angle = tan-1(latitude / longitude)
* year_recorded = year of date_recorded
* year_difference = year_recorded - construction_year

3. Tried StandardScaler and MinMaxScaler for numerical variables

* StandardScaler gave better performance

4. Applied RareLabelEncoder, OneHotEncoder, and OrdinalEncoder to encode categorical variables

* RareLabelEncoder and OneHotEncoder: `basin`, `extraction_type`, `extraction_type_group`, `extraction_type_class`, `management`, `management_group`, `payment`, `payment_type`, `water_quality`, `quality_group`, `source`, `source_type`, `source_class`, `waterpoint_type`, `waterpoint_type_group`

* OrdinalEncoder: `date_recorded`, `funder`, `installer`, `wpt_name`, `subvillage`, `scheme_management`, `region`, `lga`, `ward`, `public_meeting`, `recorded_by`, `scheme_name`, `permit`, `quantity`, `quantity_group` 

5. Since the distribution of the target class is not symmetric, tried over sampling and under sampling

* over sampling gave better performance

6. Tried PCA to reduce dimensionality

* with this performance was dropped

7. For modelling tried CatBoostClassifier, RandomForestClassifier, XGBClassifier, MLPClassifier (Neural Network)

* RandomForestClassifier gave the best performance

8. Did post processing and identified the top 20 most important features for the model. Retrained the model only with this 20 features

* with this performance was dropped

## Best score and final rank

* score: 0.8223
* rank: 690

<img width="396" alt="Final_rank" src="https://user-images.githubusercontent.com/47142899/133824911-e0a95570-4886-44bd-8f3c-ee4781a91a2b.PNG">

## All submissions made

<img width="396" alt="All_submissions" src="https://user-images.githubusercontent.com/47142899/133824964-cec22003-ef54-4752-959b-e73ac332a8ea.PNG">

