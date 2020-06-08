# MSDS-498: Data Engineering Capstone: Serverless-Data-Pipeline-Architecture implementation

## References:
__Gift, N (2020) Python for DevOps. (Links to an external site.) Sebastopol, CA: O'Reilly. [ISBN: 9781492057697]__

__Noah Gift, Robert Jordan, Kennedy Behrman, Data Engineering with Python and AWS Lambda LiveLessons, https://learning.oreilly.com/videos/data-engineering-with/9780135964330__

__https://github.com/noahgift/awslambda__

## Synopsis:
This is an attempt to recreate a reference architecture with the intention of completing a data engineering capstone project and
also learning the services and technologies along the progress. 

This is a submission for the individual project under category IV per the below definition.

Project:  Serverless Data Engineering Pipeline
Reproduce the architecture of the example serverless data engineering project.
Enhance the project by extending the functionality of the NLP analysis:  adding entity extraction, key phrase extraction, or some other NLP feature.

## Architecture Diagram:

![Architecture_Diagram](https://github.com/shankarfierce/MSDS-498/blob/master/MSDS%20498_%20Data%20engineering%20project.jpg)

1. Cloudwatch is schduled to run at defined interval to trigger lambdaproducer.
1. lambda producer pulls the reference data from Dynamo db table and pushes it to SQS.
1. SQS triggers lambda consumer.
1. lambda consumer searches the wikipedia articles with the keyword and extracts the summary.
1. summary is passed on to comprehend to conduct sentiment analysis and also extract entity recognition.
1. lambda consumer then pushes the dataframe with required attributes to amazon S3.
1. Athena sits on amazon s3 to query the data.
1. Quicksight connects to Athena as a data source for its dataset and publishes dashboard with required analytics.

## Prerequisies:
1. AWS Console access
2. Role for Lambda
3. S3 bucket creation

## Configuiring the Cloud9 IDE service in AWS
1. Create a Cloud9 IDE environment for deploying AWS Lambda function and application.
   1. Walk through the steps of creating an environment with default steps.

## Create a DynamoDb table (key value store)
## Setup SQS queue
## Create a producer lambda
## Create a consumer lambda
## Create an athena database and external table
## Configure Quicksight
