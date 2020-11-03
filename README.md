# Simple-outlier-detection

## Purpose of Project: 
The purpose of the project is to compute and visualize outliers in a time series by preparing and aggregating the raw data upfront. 

## Explanation of Data & Workflow:
The raw data is a Kaggle competittion data named 'avazu-ctr-prediction'. the dataset is commprised of many categorical but the analysis was concentrated on the on CTR and time series relevant fields, namely 'click' and 'hour' variables. The following workflow was applied in the analysis:
####         Data Preparation
                            * Downloaded and unzipped dataset (train.gz) to extract the .csv file.
                            * Extracted the columns of interest (click and hour) to create the CTR_click.csv file.
                            *Read and load csv file using pandas read_csv method
                            *checked file information, data type, completenes(missingnes)
                            * Ran summary statistics on file
                            *converted the hour datatype from int64 to datatime data type
####       Data Aggregation 
                            *create an ubset of clicks from the click column and aggregate same per hour
                            *create the impressions per hour by aggregating the click/nonclick in the click column per hour
####       Calaulate CTR
                            *calcualte CTR = clicks/impressions (total clicksper hour / impressions per hour
####       CTR Visualization
                            * the CTR timeseries data was visualized in a plot using Matloplib Python package. 
                            
####       Outlier detection model Method 1 - IQR(interquartile range)
                            * The outlier detection model was first created using the IQR - Interquartile range method to find the difference between q3 (75th) and q1                                 (25th) percentile. And later applying the 1.5*IQR to calculate the upper and lower limits to determine the outliers. 
                            *The boxplot was used to find the outliers which were below the lower limit. 
####       Outlier detection model Method 2 - Pycaret Anomaly detection module
                            * The second method applied in the creating the outlier method was through the Pycaret model. PyCaret’s Anomaly Detection Module is an                                   unsupervised machine learning module that is used for identifying rare items events or observations which raise suspicions by differing                                 significantly from the majority of the data. 
                            * The module's pre-processing features was used prepare the CTR data for modeling through it's setup function. 
                            * Tow of the module's 12 ready-to-use algorithms namely 'iforest' and 'knn' were used to create the outkier detection module.
                            * The module's 3D plots were used to analyze the results of trained models.


## Explanation of Files:
CTR_train: this is the ctr file that was used for the analysis. It is a subset of the avazu-ctr-prediction train.gz kaggle file as it is comprised primarily of columns of interest nmely 'hour' and 'click' respectively.
Outlier detection jupyter notebook: this is the notebook with the python codes for the project.

## How To Run Project



## Reference
[1] Pycaret Anomaly detection module - website: (https://pycaret.org/anomaly-detection/)
 Accessed: 30-10-2020
