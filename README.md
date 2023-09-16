# Real-Time Stock Data Pipeline

## Overview

This project demonstrates the creation of a real-time data pipeline for streaming stock data and enabling real-time analytics. The pipeline employs various AWS services, including Kafka, AWS Glue, Amazon Athena, Lambda, and SNS, to seamlessly capture, process, and deliver live stock data.

![image](https://github.com/amalprem/Realtime-Stock-Analysis-using-Kafka-and-AWS/assets/37649277/0ff452da-bb30-4ed8-aab9-0fe3ea7e13f5)

## Key Components

### Kafka Streaming

- An EC2 instance hosts Kafka, serving as the streaming platform.
- A Kafka producer script generates real-time stock data.
- A Kafka consumer script, also hosted on an EC2 instance, loads the real-time JSON stock data to AWS S3.

## AWS Glue Crawler and Athena Integration

### AWS Glue Crawler: Automated Schema Handling

- **Schema Inference**: AWS Glue Crawler automatically infers the schema of real-time stock data stored in AWS S3. This automation simplifies schema detection and adaptation, even when the data structure evolves over time.

- **Metadata Repository**: The AWS Glue Data Catalog serves as a central metadata repository that contains essential information about the real-time data generated in the pipeline. It stores details such as table definitions, data types, and transformations applied, making it easier to manage and query the data.

### Amazon Athena: Efficient Data Querying

- **Seamless Data Analysis**: Amazon Athena is utilized to perform efficient and ad-hoc SQL-based queries on the real-time stock data stored in AWS S3. By leveraging the metadata stored in the Glue Data Catalog, Athena provides a seamless and user-friendly interface for data analysts and engineers to explore and analyze the data.

- **Flexibility and Agility**: With Athena, we have the flexibility to write and execute SQL queries without the need to set up complex data infrastructure. This agility allows us to gain insights rapidly and adapt to changing data analysis requirements.


### Real-Time Notifications

- AWS Lambda is employed to create a serverless function.
- Amazon SNS (Simple Notification Service) is used for real-time email notifications.
- Whenever a new file lands in AWS S3, a notification is sent via email to subscribed users, providing them with timely updates.


### Prerequisites

- An AWS account with the necessary permissions to create and manage AWS resources.
- EC2 instances with Kafka installed for streaming.
- Lambda function configured for S3 event triggers.
- SNS topic set up for email notifications.

