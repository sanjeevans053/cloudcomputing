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

#### PLACEHOLDER IMAGE FOR INSIGHTS AND TRENDS ####
## How to Run the Project

### Upload Datasets
1. **Upload the Datasets**: 
   - Navigate to the AWS S3 console and create a new S3 bucket (or use an existing one) to store the 2023 and 2024 water permit datasets.
   - Upload the Excel files into separate folders within the bucket, organized by year (`/2023/` and `/2024/`).

### Configure AWS Glue
2. **Set Up AWS Glue Jobs**:
   - Open the AWS Glue console and create a new job to handle data cleaning and transformation.
   - Define the ETL process by specifying the input as the S3 bucket with the uploaded datasets.
   - Set up transformations such as standardizing column names, handling missing data, and adding a `year` column to facilitate comparisons between 2023 and 2024 datasets.
   - Define the output path in S3 where the cleaned data will be stored.

### Run the Data Pipeline
3. **Execute the AWS Glue Jobs**:
   - Trigger the Glue jobs to process the uploaded datasets.
   - The jobs will clean and transform the raw data and store the processed data in the specified output S3 bucket, ready for analysis.

### Data Analysis
4. **Analyze the Data**:
   - Once the data is processed and stored in the curated S3 bucket, download the cleaned CSV files.
   - Import the datasets into Excel or any preferred tool for further analysis.
   - Perform descriptive and diagnostic analyses to identify trends, patterns, and anomalies in the water permit data.

### Generate Dashboards
5. **Create Dashboards in Excel**:
   - Use Excel to generate visualizations such as line charts, bar charts, and pie charts.
   - Summarize key insights from the data analysis, including permit issuance trends, approval rates, and regional activity.
   - Export the final dashboard as a PDF report for stakeholders.
