# BostonHousing-Prediction
This project predicts housing data in boston using one-dim lasso, random forest and xgboost anc compare the accuracies.

## Preprocess:
1. Through histogram th e data is actually skewed , in o rde r to make the target normal dis tributed
the transf ormation of taking log form should be made.

2. Deal with missing values. I found that only Garage_Yr_Blt has 159 missing values based on
common sense, garage is usually built with the house. Besides there are 2227 of 2930 whose
Garage_Yr_Blt == Year_Built. Therefore I use Year_Built to fill in the missing values.

3. Feature selection. Considering all data are from the same state, their Longitudes and Latitudes
are similar, so Longitude and Latitude should b e dropped. Aside from that, I found a few
dominant features which a large portion of observations only take the specific value. Those
dominant columns should be dropped too.

4. Handle categorical data. There are 38 categorical data which is over 50 % of features. I use caret
to perfrom one hot encoding to make all predictors numeric.

## Model 1:
RandomForest is considered first but the RSME is high.
Therefore, I use a simple lasso model by using cv.glmnet to find to lambda
Accuracy : 0.124

## Model 2:
Xgboost
Accuracy 0. 128
