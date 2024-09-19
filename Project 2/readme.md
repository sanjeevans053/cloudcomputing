## _Project 2 Title: Professional Development Data Analysis Platform for UCW HR Office_

## Table of Contents
1. [Objective](#objective)
2. [Dataset](#dataset)
   - [Source](#source)
   - [Fields](#fields)
3. [Methodology](#methodology)
   - [1. Data Collection and Storage](#1-data-collection-and-storage)
   - [2. Data Cleaning and Transformation](#2-data-cleaning-and-transformation)
   - [3. ETL Pipeline Design](#3-etl-pipeline-design)
   - [4. Data Analysis](#4-data-analysis)
   - [5. Data Protection and Governance](#5-data-protection-and-governance)
   - [6. Data Monitoring](#6-data-monitoring)
   - [7. Data Visualization](#7-data-visualization)
   - [8. Data Publishing](#8-data-publishing)
4. [Tools and Technologies](#tools-and-technologies)
   - [AWS Services](#aws-services)
   - [Data Visualization](#data-visualization)
   - [Additional Tools](#additional-tools)
5. [Deliverables](#deliverables)
6. [Outcomes and Insights](#outcomes-and-insights)
7. [Conclusion](#conclusion)

### Objective
The objective of this project was to analyze and manage professional development data for UCW HR Office. The project involved creating a data platform that stores, processes, and provides insights into the university’s professional development activities, tracking employee participation, costs, and compliance with UCW policies.

![Screenshot (771)](https://github.com/user-attachments/assets/6526637f-e726-4bd6-8908-71ed53eedad5)

![Screenshot 2024-07-10 160412](https://github.com/user-attachments/assets/8e43ac86-ea5a-4ba1-aa9e-fa3bea3ace29)

**Created AWS Account** 
![Screenshot (729)](https://github.com/user-attachments/assets/0e14d747-f578-4244-a3dc-515e71046df4)


### Dataset

**_Source:_** Professional Development datasets were downloaded from the ChatGPT.

*Employee IDs:* Unique identifiers for staff.

*Professional Development Activities:* Conferences, courses, and workshops attended.

*Costs:* Costs associated with professional development activities.

*Approval Status:* Whether activities were approved or pending....

*Completion Records:* Proof of completed activities and expenses.
![Screenshot (771)](https://github.com/user-attachments/assets/194346bb-1b6b-4411-9e97-c165befe533e) 

### Methodology

#### 1. Data Collection and Storage

**_Data Acquisition:_** Professional development activity data was collected from UCW HR’s internal systems.

**_Storage Solution:_**
  
  - The dataset was uploaded and stored in AWS S3.
  
  - Data was organized into S3 landing zones, categorized by year and employee department.
  
  - Security: KMS encryption was applied to protect sensitive employee data.

![Screenshot (770)](https://github.com/user-attachments/assets/502a67bc-8155-4819-8891-7c5c5a7d629b)


#### 2. Data Cleaning and Transformation

**_Data Preparation Using AWS Glue DataBrew:_**

  - Fields like Employee IDs, Professional Development Type, and Costs were standardized.
  
  - A "Year" column was added to facilitate the dataset.
  
  - Cleaned data was stored in the Raw S3 bucket.

![image](https://github.com/user-attachments/assets/f3fab158-58fa-447f-bfe3-6f3208e1a266)


#### 3. ETL Pipeline Design

**_ETL Pipeline Design:_**

  - An ETL (Extract, Transform, Load) pipeline was designed using Draw.io to map the data flow from the Landing S3 bucket to the Curated S3 bucket.
  
  - Key transformations included renaming columns for consistency, filtering out unnecessary data, and aggregating the tax levy datasets.


![Screenshot (802)](https://github.com/user-attachments/assets/17a1a03f-1862-4922-9c92-65e68a8649df)

![Screenshot (803)](https://github.com/user-attachments/assets/8c9d7354-872b-4526-b236-72b29b344c2e)

![Screenshot (804)](https://github.com/user-attachments/assets/cb22ae6e-aab1-41bd-8cb8-b775360bb4aa)

 


**_ETL Implementation Using AWS Glue:_**

  - The ETL pipeline was implemented in AWS Glue to extract data from the Raw S3 bucket, transform it,... and load it into the Curated S3 bucket.

![Screenshot 2024-07-29 135057](https://github.com/user-attachments/assets/3e78a691-ea17-48f3-9507-a2c0458bd4d7)


#### 4. Data Analysis

**Amazon Athena was used for creating external tables:**

**_SQL Queries:_** SQL was utilized only for creating tables to organize the datasets in Athena and point to the curated data stored in S3.

![image](https://github.com/user-attachments/assets/f478961d-6148-4303-a186-843f3b2c1a51)
 

**_Data Analysis:_**

  - Excel was used to analyze trends in professional development activities, costs, and approval rates across departments.
  
  - This analysis allowed UCW HR to identify key areas of spending, compliance, and professional growth for employees.

#### 5. Data Protection and Governance:

**_Data Encryption:_** KMS keys were used to encrypt all data stored in S3.
![image](https://github.com/user-attachments/assets/c841f1bf-beba-4c7d-8dc8-8b1ba8fa1bf6)


**_Backup and Replication:_**

  - A backup S3 bucket was created to ensure data availability in case of failures.
  
  - Replication rules were applied to securely transfer data between the primary and backup S3 buckets using the same KMS encryption.
  
  - Automated Data Governance: AWS Glue was used to conduct regular data quality checks, with a scheduled automation process ensuring data consistency and accuracy.

![image](https://github.com/user-attachments/assets/aaf7c3d9-b255-47d0-9ae3-b5a9c00495a6)


#### 6. Data Monitoring

Amazon CloudWatch and AWS CloudTrail were employed for continuous monitoring and tracking:

CloudWatch was used to monitor key metrics such as resource consumption and cost estimations.

![image](https://github.com/user-attachments/assets/aa80463d-6fbb-45ab-8e2a-dacd8e007eb0)


CloudTrail tracked all user activities and API calls, storing the logs in S3 for audit purposes....


#### 7. Data Visualization

**_Visualization Tools:_**

Excel was utilized to create interactive charts such as pie, bar, and line graphs.

A dashboard was created to present insights, including professional development costs and trends.


#### 8. Data Publishing:

**_Server Setup:_**

EC2 Instances were configured to host and publish the processed data and visualizations.

The processed datasets were made accessible to stakeholders via a web interface hosted on the EC2 instances.


**_Data Storage:_** The transformed data and visual reports were uploaded to Remote access, allowing for easy access and sharing among stakeholders.

### Tools and Technologies

**_AWS Services:_**

S3: Data storage and management.

AWS Glue: Data cleaning, transformation, and ETL pipeline implementation.

Amazon Athena: SQL queries for table creation and dataset management.

Amazon CloudWatch: System monitoring.

AWS CloudTrail: Audit logs and user activity tracking.

KMS Encryption: Data security.

EC2 Instances: Web hosting and report publishing.

**_Data Visualization:_**

Excel: Used to generate interactive visualizations such as charts and dashboards.

Draw.io: Used for visualizing the ETL pipeline workflow.

**Amazon SageMaker:**

Used for processing emails and extracting relevant data for table creation.

SageMaker's machine learning capabilities were applied to identify and structure key information from emails related to professional development activities....



**DynamoDB**

Structured tables were created in DynamoDB from the extracted email data, allowing for seamless integration into the overall analysis pipeline. 

These tables contained structured data, such as employee professional development requests and related approvals.

### Deliverables

A complete ETL pipeline implemented using AWS Glue, enabling automated data processing for professional development tracking.

Interactive Excel dashboards displaying trends in employee participation, professional development costs, and approval status.

Web-accessible reports hosted on EC2 instances, allowing stakeholders easy access to data insights.

A comprehensive report summarizing trends, costs, and compliance with professional development policies.

Tables generated from email data using Amazon SageMaker and DynamoDB, providing an automated method of capturing and organizing professional development requests from employee communications.


### Outcomes and Insights

*1. Participation Trends:* Analyzed professional development participation rates by department, identifying areas with higher engagement.
*2. Cost Breakdown:* Provided detailed insights into the financial resources allocated for professional development across different departments...
*3. Approval Status:* Tracked the approval process for professional development requests...
*4. Email Data Integration:* Using Amazon SageMaker...
*5. Recommendations:* Suggested improvements...

### Conclusion...

This project successfully built a data platform...
