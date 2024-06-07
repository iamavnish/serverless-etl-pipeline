# Serverless ETL Pipeline on AWS

## Overview 

This is Proof of Concept for Serverless ETL Pipeline on AWS. 

## Architecture

![serverless-etl-pipeline drawio](https://github.com/iamavnish/serverless-etl-pipeline/assets/13760927/16fb7b59-ccf2-4874-82ae-1f3666f9666b)

## Tech Stack

- AWS
  - Lambda
  - S3
  - Glue Crawler
  - Glue Catalog
  - Athena
  - IAM
  - CloudWatch Events (EventBridge)
  - CloudWatch Logs
- Python3

## Dataset

Top 50 Songs Globally on Spotify accessed through Spotify API

## Solution

Stock market events are being sent to Kafka Producer application which in turn writes them to Kafka topic. Kafka Consumer application reads those events from Kafka topic which are further written to files in S3 bucket. Glue Crawler determines the schema of data stored in S3 bucket and creates metadata in Glue Catalog. Then data from files stored in S3 bucket is being queried for insights through Athena.
