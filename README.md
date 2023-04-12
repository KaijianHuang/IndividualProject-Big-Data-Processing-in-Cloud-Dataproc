# IDS-04-Data

## Introduction
In this project, we are going to build a major Big Data system to perform a Data Engineering related task.    

My project is weather prediction. 

I use AWS S3 to store my data and use AWS Sagemaker to do machine learning model code part. A model is built to predict the loan based on the data we provided, and we also calculate the accuracy of our model compared with real data.    

## Data Analysis
In this loan prediction dataset, we have the infomation of applicants those who previously applied for the loan.   

The database is collected from Kaggle.

## Code Overflow

1. import important module   
2. import data file. If we do it locally, local address is needed; if we import data through AWS S3, sagemaker module is needed.
```
from sagemaker import get_execution_role
role = get_execution_role()
bucket='ids721-project4'
train_key = 'weatherAUS.csv'
data = 's3://{}/{}'.format(bucket, train_key)
```
3. data anlysis   
4. data cleaning   
5. build model and do evaluation

## Data Result
```
              precision    recall  f1-score   support

           0       0.86      0.97      0.91     20110
           1       0.76      0.40      0.52      5398

    accuracy                           0.85     25508
   macro avg       0.81      0.68      0.72     25508
weighted avg       0.84      0.85      0.83     25508

              precision    recall  f1-score   support

           0       0.86      0.97      0.91     20110
           1       0.76      0.40      0.52      5398

    accuracy                           0.85     25508
   macro avg       0.81      0.68      0.72     25508
weighted avg       0.84      0.85      0.83     25508
```

## Steps
1. create a bucket on AWS S3    
<img width="500" alt="s3-setup" src="/Screenshot 2023-04-12 at 15.42.56.png">
2. upload our data to AWS S3
<img width="500" alt="s3-upload" src="/Screenshot 2023-04-12 at 15.44.38.png">
3. create a notebook instance in AWS Sagemaker
<img width="500" alt="sage-setup1" src="/Screenshot 2023-04-12 at 15.54.58.png">
4. create a IAM role for sagemaker AWS

5. the notebook instance is created successful after wait

6. click "open jupyter" and create "conda_python3" file and do code there
  

## Requirement
1. Use a major Big Data system to perform a Data Engineering related task

2. Example systems could be: (AWS Athena, AWS Spark/EMR, AWS Sagemaker, Databricks, Snowflake)

## Reference
1. https://www.kaggle.com/code/karnikakapoor/rain-prediction-ann/notebook
