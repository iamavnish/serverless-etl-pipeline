# Serverless ETL Pipeline on AWS

## Overview 

This is Proof of Concept for Serverless ETL Pipeline on AWS. 

## Architecture

![Architecture](https://github.com/iamavnish/stock-market-data-analysis/assets/13760927/5ba38201-3c3e-4fbd-8ff1-c5f9da943146)

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

Spotify API - Top 50 Songs Globally

## Solution

Stock market events are being sent to Kafka Producer application which in turn writes them to Kafka topic. Kafka Consumer application reads those events from Kafka topic which are further written to files in S3 bucket. Glue Crawler determines the schema of data stored in S3 bucket and creates metadata in Glue Catalog. Then data from files stored in S3 bucket is being queried for insights through Athena.

## Simulation

To simulate a stream of stock market events, a pandas dataframe is being created from CSV file containing stock market data. Then dataframe's random function is being invoked in a loop to return random rows from the dataframe, one at a time.
