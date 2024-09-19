# Water Permits Data Analysis (City of Vancouver)

This project analyzes and visualizes water permit status data from the City of Vancouver for the years 2023 and 2024. Using AWS and advanced data analytics tools, the aim is to uncover trends, implications, and actionable insights to assist decision-makers. The project follows a complete data pipeline lifecycle, from data collection to visualization and reporting.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Dataset and Methodology](#dataset-and-methodology)
- [Data Pipeline](#data-pipeline)
- [Data Analysis](#data-analysis)
- [Data Visualization](#data-visualization)
- [Key Results and Insights](#key-results-and-insights)
- [How to Run the Project](#how-to-run-the-project)

## Project Overview
The project involves:
- Analyzing water permit data from 2023 and 2024.
- Identifying trends and insights from permit activities, approval rates, and geographic distribution.
- Building a secure and scalable data pipeline using AWS services.
- Presenting visual insights through Excel dashboards to stakeholders.

#### PLACEHOLDER IMAGE FOR PROJECT OVERVIEW ####

## Technologies Used
- **AWS S3**: Scalable storage for raw and processed datasets.
- **AWS Glue**: For data cleaning, transformation, and ETL pipeline management.
- **AWS Athena**: For querying data stored in S3 buckets.
- **Excel**: For visualizing the results through interactive charts and dashboards.
- **Python**: For scripting automation tasks and additional data processing.

#### PLACEHOLDER IMAGE FOR TECHNOLOGIES ####

## Dataset and Methodology
The datasets used in this project were sourced from the **City of Vancouver Open Data Portal**. The water permit data for 2023 and 2024 contains information such as permit issuance date, approval status, property type, region, and activity type (new installations, repairs, etc.).

### Data Collection Methodology
1. **Open Data Portal**: 
   - Access the City of Vancouver Open Data Portal to retrieve water permit datasets.
   - Download the datasets for 2023 and 2024 in Excel format.

2. **Data Profiling**:
   - Profile the datasets to understand their structure and contents.
   - Identify any missing or incomplete data that needs to be cleaned before analysis.

3. **Data Fields**:
   - **Permit ID**: A unique identifier for each water permit.
   - **Issue Date**: The date the permit was issued.
   - **Approval Status**: Whether the permit is approved, pending, or rejected.
   - **Property Type**: The type of property (residential, commercial, etc.).
   - **Region**: The geographic region of the permit issuance.
   - **Permit Activity**: Type of water-related work (new installations, repairs, etc.).

![image](https://github.com/user-attachments/assets/1ff752c7-f106-48f3-96e3-0e98312ba6aa)

## Data Pipeline
A well-structured data pipeline was designed to process and prepare the water permits data:

1. **Data Ingestion**: Water permit datasets (Excel files) were uploaded to AWS S3, organized by year in dedicated buckets.
2. **Data Cleaning and Transformation**: AWS Glue DataBrew was used for:
   - Cleaning data to remove inconsistencies and handle missing values.
   - Adding a **year** column to facilitate year-over-year comparisons.
   - Standardizing column formats.
3. **Data Storage**: Cleaned datasets were stored in AWS S3 under a **Raw Data** section for future analysis.
4. **ETL Pipeline**: AWS Glue was used to transform the data for downstream analysis. The ETL process involved steps such as:
   - Aggregating data.
   - Ensuring data consistency across 2023 and 2024.
   - Preparing the data for further analysis.

![image](https://github.com/user-attachments/assets/bf95ba1d-0135-4da5-9ba2-07567031a22b)

## Data Analysis
Once the data was cleaned and transformed, it was ready for analysis. Key tasks included:

- **Descriptive Analysis**: To observe trends in the issuance, approval rates, and activities of water permits over time.
- **Diagnostic Analysis**: Investigating the reasons for any observed patterns or anomalies, such as sudden changes in permit activity.
- **Predictive Analysis**: Based on historical trends, predictions were made for future water permit activities.

![image](https://github.com/user-attachments/assets/23f2d30c-db19-4748-935b-4b9ce2c1ff4a)

## Data Visualization
Due to budget constraints, **Excel** was used for visualization. The cleaned datasets were imported into Excel, where various charts and dashboards were created:

- **Year-over-Year Trends**: A line chart showing how the number of issued permits has changed from 2023 to 2024.
- **Approval Status Breakdown**: A pie chart illustrating the proportion of approved, rejected, and pending permits.
- **Permit Activity by Region**: A bar chart displaying the number of permits by geographic region and property type.

These charts were then integrated into an interactive Excel dashboard and exported as a PDF report for stakeholders. The dashboard enables easy interpretation and action on the data-driven insights.

![image](https://github.com/user-attachments/assets/e3b795ae-399f-4a87-bc5f-093f6d541776)

## Key Results and Insights
From the analysis, the following insights were gathered:

- **Trend in Issuances**: The number of water permits issued in 2024 saw a significant increase compared to 2023, driven primarily by growth in residential developments.
- **Improved Approval Rates**: In 2024, the approval process showed improvements, with fewer pending permits than in 2023.
- **Regional Differences**: Specific regions of Vancouver displayed higher water permit activity, indicating targeted infrastructure projects or local regulations driving these trends.
- **Future Projections**: Based on the trends, an increase in water permits for 2025 is anticipated, particularly in new residential installations and repairs.

![image](https://github.com/user-attachments/assets/136111dc-be6c-4874-a6f8-f8d1965cc6bf)


## Data Protection

Data protection in this project is critical, particularly as it involves sensitive information such as personal identifiers from the City of Vancouver Water Permit datasets. The project ensures the security of this data through the following key AWS services:

### AWS Glue & AWS Crawler
- **Sensitive Data Masking**: AWS Glue was used to mask sensitive information in the dataset. This ensures that personal data, such as individual identifiers, is not exposed to unauthorized users. AWS Glue’s automated ETL processes enabled the identification and transformation of personal data fields into anonymized values.
- **Data Crawling for Schema Updates**: AWS Crawler scanned the datasets to automatically detect and update the schema, ensuring that any changes or new datasets were efficiently integrated into the pipeline while maintaining security protocols.

### AWS IAM Roles
- **Access Control with IAM Roles**: Role-based access control was configured using AWS Identity and Access Management (IAM). Only authorized users with specific roles (e.g., data engineers, analysts) were granted access to the data for reading, writing, or processing. Unauthorized access attempts were logged for auditing purposes.
  
![image](https://github.com/user-attachments/assets/9734153e-19f5-4b78-9b37-6f8f5bdcbebc)
  
### AWS KMS (Key Management Service)
- **Data Encryption**: AWS KMS was employed to manage encryption keys, ensuring all sensitive data was encrypted both at rest and in transit. This added an extra layer of protection, ensuring that even if unauthorized access to the dataset occurs, the data remains encrypted and inaccessible.
  

- **Backup and Replication**: Backups of water permits data were regularly performed, and replication rules were configured to store encrypted data in different geographic regions to ensure redundancy and disaster recovery.

![image](https://github.com/user-attachments/assets/380ff4d0-d8c3-459a-97fb-dfd180609a87)

![image](https://github.com/user-attachments/assets/7205c416-3fc9-4aa5-b816-946f43c95af8)

## Data Governance

Effective data governance was key to maintaining control over access, usage, and security of the water permits data. Two critical AWS services were utilized:

![image](https://github.com/user-attachments/assets/68c69217-dbb8-4a3b-8465-0d458080c0cf)

### AWS IAM (Identity and Access Management)
- **Controlled User Access**: AWS IAM was employed to regulate access to sensitive data. IAM policies ensured that access was restricted to authorized individuals based on roles, preventing accidental or malicious access by unauthorized users. Users were segmented based on their roles—data engineers had full access to modify the pipeline, while analysts were granted read-only access.

### AWS KMS (Key Management Service)
- **Key Creation and Control**: AWS KMS created and managed encryption keys for the water permits dataset. These encryption keys ensured that data remained confidential and was only accessible by those who were authorized.
  

## Data Monitoring

AWS services played a crucial role in monitoring and maintaining the operational health and security of the data infrastructure:

### AWS CloudWatch
- **Real-Time Monitoring**: AWS CloudWatch was configured to monitor key performance metrics, including job executions, data processing times, and overall pipeline health. It enabled the team to observe real-time metrics and logs related to the ETL pipeline and other AWS services used in the project.
- **Alarms and Thresholds**: CloudWatch alarms were set up to notify the team when certain performance thresholds were exceeded (e.g., job failures, high memory usage), enabling a proactive response to issues.

 ![image](https://github.com/user-attachments/assets/8b1f210d-846f-4e75-800c-2a4ecfeec979)



![image](https://github.com/user-attachments/assets/11c383e1-3688-48a1-aad9-7d11b61c90dc)


## CloudTrail

![image](https://github.com/user-attachments/assets/36b43b81-0419-426d-8708-f49c7a5faa1b)


### QRPR ETL Job Monitoring
- **Job Status Monitoring**: QRPR ETL jobs were monitored to ensure successful completion. Any job failures were logged and reported through CloudWatch, prompting an alert for immediate investigation.

  ![QRPR ETL Job Status](path/to/qrpr_etl_status_image)

