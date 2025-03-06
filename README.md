#End-To-End Data Engineering Project in | AWS | Snowflake | DynamoDB | Realtime Project

![image](https://github.com/user-attachments/assets/1a4e96ab-9f0f-47bd-a6fc-882bc8d868bd)



Developed and Implemented Real-Time Weather Data Ingestion Pipeline

Weather API Integration: Designed and integrated a system to fetch real-time weather data from external Weather APIs.

AWS Services Utilization: Leveraged AWS EventBridge for event-driven architecture to trigger data ingestion workflows, and AWS Lambda for serverless processing of weather data.

Data Storage: Utilized DynamoDB to store weather data in a scalable NoSQL database, ensuring high availability and low-latency access.

Data Processing & Storage: Automated data storage in AWS S3 for reliable, cost-effective storage of raw and processed data.

Data Ingestion to Snowflake: Developed ETL processes to efficiently ingest processed weather data into Snowflake for analytics and reporting.

Optimized and Scalable Solutions: Ensured the pipeline's scalability and efficiency by implementing serverless and event-driven technologies across the entire data flow.

STEPS:


Get the Weather API-Free -weatherAPI.com
AWS -Create a Free tier Account
Snowflake- Create 40 days Free tier Account



1.EventBridge is triggered 1 hour once- where Lambda-1 get weather details from weather api and save the details in DynamoDB

2.DynamoDb table is created with partition key -city, sort key-time

3.The weather details for the given city are inserted in DynamoDb by Lambda-1 and where DynamoDb stream(Lambda-2) is triggered for INSERT action in DynamoDb.

4.S3 Bucket is created ,with a subfolder snowflake is also created .

5.As the Lambda-2 is triggered , it get the table data and save it in s3 folder(under snowflake/) in form of seperate csv file for each city.

6.Both Snowflake and AWS , permission are established to get data from AWS S3 to Snowflake.

7.Using snowpipe, automatic ingestion of data  is set  using the sqs arn (automatically created in Snowflake) i.e when new data is inserted into S3 , event Notification SQS is set.
	
