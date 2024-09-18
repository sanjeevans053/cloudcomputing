# Water Permits Data Analysis (City of Vancouver)

This project focuses on analyzing and visualizing water permit status data for the City of Vancouver for the years 2023 and 2024. Using AWS and advanced data analytics tools, the goal is to uncover trends, implications, and actionable insights for stakeholders. The project involves data collection, storage, transformation, analysis, and visualization, showcasing the full data pipeline lifecycle.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Data Pipeline](#data-pipeline)
- [Data Analysis](#data-analysis)
- [Data Visualization](#data-visualization)
- [Key Results and Insights](#key-results-and-insights)
- [How to Run the Project](#how-to-run-the-project)

## Project Overview
The main objectives of this project are:
- Analyzing water permit data from 2023 and 2024.
- Identifying trends, anomalies, and insights to assist in decision-making.
- Building a secure and scalable data pipeline using AWS services.
- Visualizing key results using Excel dashboards for stakeholders.

#### PLACEHOLDER IMAGE FOR PROJECT OVERVIEW ####

## Technologies Used
- **AWS S3**: For data storage.
- **AWS Glue**: For data preparation and ETL pipeline.
- **AWS Athena**: For SQL-based querying and analysis.
- **Excel**: For data visualization and dashboard creation.
- **Python**: For automation and data processing scripts.

#### PLACEHOLDER IMAGE FOR TECHNOLOGIES ####

## Data Pipeline
The project employs a robust data pipeline to process water permit data. Below are the key components:

1. **Data Ingestion**: Data is ingested into AWS S3 from Excel files obtained via the City of Vancouver Open Data Portal.
2. **Data Cleaning and Transformation**: AWS Glue DataBrew is used for cleaning, standardizing, and transforming the datasets.
3. **Data Storage**: Cleaned datasets are stored in the "Raw" and "Curated" zones of the S3 buckets for further analysis.
4. **ETL Pipeline**: An AWS Glue-based ETL pipeline is designed to process and prepare data for analysis.

#### PLACEHOLDER IMAGE FOR DATA PIPELINE WORKFLOW ####

## Data Analysis
Data analysis is performed using Amazon Athena with SQL queries. The steps include:
- **Descriptive Analysis**: To identify trends in water permits.
- **Diagnostic Analysis**: To find reasons behind observed trends and anomalies.
- **Predictive Analysis**: To project future water permit trends based on historical data.

#### PLACEHOLDER IMAGE FOR SQL QUERIES IN ATHENA ####

## Data Visualization
Due to budget constraints, Excel was used for creating charts and dashboards. The insights were visualized using:
- Bar Charts
- Pie Charts
- Line Graphs

These charts were integrated into an interactive Excel dashboard, converted into a PDF report for stakeholders.

#### PLACEHOLDER IMAGE FOR EXCEL DASHBOARDS ####

## Key Results and Insights
Some of the key insights from the data analysis include:
- Year-over-Year trends in permit issuance and approval rates.
- Identification of hotspots in water permit activity across various regions and property types.
- Predicted trends in water permits for 2025 based on 2023 and 2024 data.

#### PLACEHOLDER IMAGE FOR INSIGHTS AND TRENDS ####

## How to Run the Project
### Prerequisites
- An AWS account with access to S3, Glue, and Athena.
- Python installed locally (for automation and additional data processing).
- Excel for visualization purposes.

### Steps
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/water-permits-data-analysis.git
   cd water-permits-data-analysis
