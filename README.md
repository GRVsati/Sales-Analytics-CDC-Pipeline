# Sales Analytics CDC Pipeline

## CDC Pipeline README

This repository contains code for a **Change Data Capture (CDC) pipeline** designed to capture, transform, and analyze data using AWS services.

### Overview
The CDC pipeline follows the process outlined below:

1. **Data Generation:** Mock data is generated using a Python script to simulate real-world data.

2. **Data Transfer to DynamoDB:** The generated data is transferred to Amazon DynamoDB, a fully managed NoSQL database service.

3. **Change Data Capture (CDC):**
   - **Kinesis Stream:** The CDC events are captured using Amazon Kinesis Streams, which enables real-time data streaming.
   - **Event Pipe:** An event pipe connects DynamoDB to the Kinesis stream, allowing changes in the DynamoDB table to be captured and streamed.

4. **Data Transformation and Storage:**
   - **Kinesis Firehose:** The Kinesis stream is connected to Amazon Kinesis Firehose, which automatically loads the streaming data into Amazon S3 for storage.
   - **Lambda Transformation:** A Lambda function is invoked by Kinesis Firehose to transform and extract relevant data before storing it in Amazon S3.

5. **Metadata Storage and Analytics:**
   - **Glue Crawler:** AWS Glue Crawler is used to discover and catalog metadata from the data stored in Amazon S3.
   - **Amazon Athena:** Athena, a serverless query service, is utilized for analytics on the data stored in S3, enabling ad-hoc SQL queries.

### Getting Started
To deploy and use the CDC pipeline, follow these steps:

**Prerequisites:**
- AWS account with appropriate permissions.
- Python installed on your system.
- AWS CLI configured with your credentials.

**Clone Repository:**

git clone https://github.com/your-username/cdc-pipeline.git

**Set Up AWS Resources:**

-Modify the configuration files (config.json, etc.) with your AWS credentials and specific settings.
-Deploy the necessary resources using AWS CloudFormation or the AWS Management Console.

-Run Data Generation Script:python data_generation.py

**Monitor and Analyze Data:**

-Monitor the AWS services (Kinesis Streams, Lambda, etc.) for real-time data processing.
-Use Amazon Athena to run SQL queries and analyze the data stored in Amazon S3.

**USE CASES**
- Data replication
- Data Integration
- Event Driven Architecture


### Contributing
If you'd like to contribute to the development of this CDC pipeline, feel free to fork the repository and submit pull requests. Contributions, feedback, and suggestions are welcome!
