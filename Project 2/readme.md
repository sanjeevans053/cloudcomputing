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

![Draw io, week 2](https://github.com/user-attachments/assets/e418948a-6b8c-47e6-9ae6-9d9b6a731055) 
![Screenshot 2024-07-10 160114](https://github.com/user-attachments/assets/476f95ae-9280-420b-9146-42917e486bde) 
**Created AWS Account** 
![Screenshot 2024-07-10 160158](https://github.com/user-attachments/assets/804f6bbe-0bcb-4fd2-9bdc-c9bbf11aebbf) 

### Dataset

**_Source:_** Professional Development datasets were downloaded from the ChatGPT.

*Employee IDs:* Unique identifiers for staff.

*Professional Development Activities:* Conferences, courses, and workshops attended.

*Costs:* Costs associated with professional development activities.

*Approval Status:* Whether activities were approved or pending....

*Completion Records:* Proof of completed activities and expenses.
![Screenshot (771)](https://github.com/user-attachments/assets/194346bb-1b6b-4411-9e97-c165befe533e) 
![Screenshot 2024-07-21 142953](https://github.com/user-attachments/assets/19f16db0-660a-4143-90f8-643ae96d267f) 
![Screenshot 2024-07-21 143200](https://github.com/user-attachments/assets/b98507ba-e60f-4dff-8707-7444e0f20df0) 
![Screenshot 2024-07-21 143333](https://github.com/user-attachments/assets/5a5334d8-8902-4a86-a4c0-94e73d2cfc0e) 

### Methodology

#### 1. Data Collection and Storage

**_Data Acquisition:_** Professional development activity data was collected from UCW HR’s internal systems.

**_Storage Solution:_**
  
  - The dataset was uploaded and stored in AWS S3.
  
  - Data was organized into S3 landing zones, categorized by year and employee department.
  
  - Security: KMS encryption was applied to protect sensitive employee data.

![Aws creating Folder](https://github.com/user-attachments/assets/0beb74e8-744a-4103-88d0-950283f16fbd) 

#### 2. Data Cleaning and Transformation

**_Data Preparation Using AWS Glue DataBrew:_**

  - Fields like Employee IDs, Professional Development Type, and Costs were standardized.
  
  - A "Year" column was added to facilitate the dataset.
  
  - Cleaned data was stored in the Raw S3 bucket.

![Class Participation 3](https://github.com/user-attachments/assets/eae7689c-1816-478b-a2dc-194c0f83cad3) 

#### 3. ETL Pipeline Design

**_ETL Pipeline Design:_**

  - An ETL (Extract, Transform, Load) pipeline was designed using Draw.io to map the data flow from the Landing S3 bucket to the Curated S3 bucket.
  
  - Key transformations included renaming columns for consistency, filtering out unnecessary data, and aggregating the tax levy datasets.

![ETL on DRAw io1](https://github.com/user-attachments/assets/103cb2e6-3082-4950-aad6-40f312c2df10) 
![ETL on Draw io](https://github.com/user-attachments/assets/22f9d4a1-6c68-42f4-9d64-ce628f52e3c4) 

**_ETL Implementation Using AWS Glue:_**

  - The ETL pipeline was implemented in AWS Glue to extract data from the Raw S3 bucket, transform it,... and load it into the Curated S3 bucket.

![image](https://github.com/user-attachments/assets/317d8350-5361-4169-bd4c-2d9f33e753f0) 

#### 4. Data Analysis

**Amazon Athena was used for creating external tables:**

**_SQL Queries:_** SQL was utilized only for creating tables to organize the datasets in Athena and point to the curated data stored in S3.

![image](https://github.com/user-assets/51e20f50-b23f...) 

**_Data Analysis:_**

  - Excel was used to analyze trends in professional development activities, costs, and approval rates across departments.
  
  - This analysis allowed UCW HR to identify key areas of spending, compliance, and professional growth for employees.

#### 5. Data Protection and Governance:

**_Data Encryption:_** KMS keys were used to encrypt all data stored in S3.

**_Backup and Replication:_**

  - A backup S3 bucket was created to ensure data availability in case of failures.
  
  - Replication rules were applied to securely transfer data between the primary and backup S3 buckets using the same KMS encryption.
  
  - Automated Data Governance: AWS Glue was used to conduct regular data quality checks, with a scheduled automation process ensuring data consistency and accuracy.

![class 7... ](https://github.com/user-assets/0dcd524...) 

#### 6. Data Monitoring

Amazon CloudWatch and AWS CloudTrail were employed for continuous monitoring and tracking:

CloudWatch was used to monitor key metrics such as resource consumption and cost estimations.

![Class_Participation ](https://github.com/user-assets/651...) 

CloudTrail tracked all user activities and API calls, storing the logs in S3 for audit purposes....

![Class_participation_9_2 ](https://github.com/user-assets/926...) 

#### 7. Data Visualization

**_Visualization Tools:_**

Excel was utilized to create interactive charts such as pie, bar, and line graphs.

A dashboard was created to present insights, including professional development costs and trends.

![image ](https://github.com/user-assets/cd5...) 

#### 8. Data Publishing:

**_Server Setup:_**

EC2 Instances were configured to host and publish the processed data and visualizations.

The processed datasets were made accessible to stakeholders via a web interface hosted on the EC2 instances.

![image ](https://github.com/user-assets/9d2...) 
![image ](https://github.com/user-assets/e4a...) 
![Screenshot ](https://github.com/user-assets/e82...) 

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

### Additional Tools

![Class Participation ](https://github.com/user-assets/8bf...) 

**Amazon SageMaker:**

Used for processing emails and extracting relevant data for table creation.

SageMaker's machine learning capabilities were applied to identify and structure key information from emails related to professional development activities....

![image ](https://github.com/user-assets/662...) 
![image ](https://github.com/user-assets/e1a...) 

**DynamoDB**

Structured tables were created in DynamoDB from the extracted email data, allowing for seamless integration into the overall analysis pipeline.

![image ](https://github.com/user-assets/755...) 

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
