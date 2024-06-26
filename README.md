# Serverless ETL Pipeline on AWS

## Overview 

This is Proof of Concept for Serverless ETL Pipeline on AWS. 

## Architecture

![serverless-etl-pipeline drawio](https://github.com/iamavnish/serverless-etl-pipeline/assets/13760927/dc4b75e2-ac85-49ca-bc1b-2a912bfcf71b)


## Tech Stack

- AWS
  - Lambda
  - S3
  - Glue Crawler
  - Glue Catalog
  - Athena
  - QuickSight
  - IAM
  - CloudWatch Events (EventBridge)
  - CloudWatch Logs
- Python3

## Dataset

Top 50 Songs Globally on Spotify accessed through Spotify API

## Solution

Lambda function is triggered once a day through CloudWatch Events which extracts data for top 50 global songs on Spotify through Spotify API and stores in S3 bucket in JSON format. Another Lambda function gets triggered whenever a new file is added to S3 bucket (first S3 bucket). This second lambda function does some transformations on the raw data like extracting albums data, artists data and songs data and storing the transformed data into second S3 bucket in CSV format. Schema is inferred from CSV files through Glue Crawlers and corresponding metadata is stored in Glue Data Catalog. Then anaytics can be performed on top of CSV files in second S3 bucket using Athena service. Finally, a dashboard is built using QuickSight to visualize data such as "Top 5 Global Artists on Spotify" using Athena as Data Source.

[Top 5 Global Artists (Dashboard).pdf](https://github.com/user-attachments/files/15949227/Top.5.Global.Artists.Dashboard.pdf)


