# Azure End to End Data Engineering Pipeline

This project builds an End-to-End Azure Data Engineering Solution. A Pipeline performing Data Ingestion, ETL and Analytics all-in-one solution using Microsoft Azure Services and Power BI.

## Goal of the Project

The goal is to create an Azure solution which can take an On-premise Database such as the Microsoft SQL Server Management System (SSMS) and move it to the Cloud. It does so by building an ETL pipeline using Azure Data Factory, Azure Databricks and Azure Synapse Analytics.

This solution can be connected to a visualization and reporting dashboard using Microsoft Power BI.

![image](https://github.com/zBalachandar/AdventureWorks-Sales-Data-Analytics-Azure-Data-Engineering-End-to-End-Project/Home.png)


Data Migration to the Cloud is one of the most common scenarios the Data Engineers encounter when building solutions for a small-medium organization.
By working on this project, I was able to learn these skills:

* Data Ingestion
* ETL techniques using Azure Cloud Services
* Data Transformation
* Data Analytics and Dashboard Reporting
* Data Security and Governance


## Prerequisites:

1) Microsoft SQL Server Managment System (SSMS)
2) Azure Subscription (Azure Data Lake Storage Gen2, Azure Data Factory, Azure Key Vault, Azure Databricks, Azure Synapse Analytics, Microsoft Entra ID)
3) Microsoft Power BI
4) Set up "AdventureWorksLT2017" Database with credentials 'usr1'. Set up the same credentials as Secrets in Azure Key Vault

The Database used for this project demonstration is:
AdventureWorksLT2017 Sales Database
[]

## Implementation:

### Part 1: Data Ingestion

Ingested data from an on-premises SQL Server into Azure Data Lake Storage Gen2 using Azure Data Factory. Configured Integration Runtime for hybrid connectivity and stored data in optimized Parquet format within a Bronze layer for efficient downstream processing.
   
   ![image](https://github.com/zBalachandar/AdventureWorks-Sales-Data-Analytics-Azure-Data-Engineering-End-to-End-Project/blob/main/pix/SOURCE%202017LTv1.png)

### Part 2: Data Transformation

Performed multi-stage data transformations using Azure Databricks (PySpark). Implemented the Bronze → Silver → Gold data architecture:

   * Bronze to Silver: applied schema/type standardization and preliminary cleaning.

   * Silver to Gold: enforced consistent naming conventions, business-friendly formatting, and transformation logic.
     Final Gold-level datasets were stored in Delta format, optimized for analytics and reporting.


### Part 3: Data Loading

Automated the movement of curated Gold data into Azure Synapse Analytics. Designed a pipeline that dynamically retrieved table metadata and executed stored procedures to create/update SQL views. This enabled scalable, query-ready data models for reporting and business intelligence.

![image](https://github.com/Shashi42/Azure-End-to-End-Sales-Data-Analytics-Pipeline/assets/26250463/7f935213-4dd9-471a-aa24-bc4b1c68f41b)


### Part 4: Data Reporting

Connected Microsoft Power BI directly to Synapse views using DirectQuery for real-time analytics. Developed interactive dashboards highlighting sales performance, product trends, and customer insights. Configured automated refresh to ensure reports always reflect the latest processed data.


### Part 5: End-to-end Pipeline Testing

Validated the complete pipeline by scheduling automated triggers in Azure Data Factory for daily refresh cycles. Confirmed data lineage from ingestion to reporting and ensured governance/security using Azure Key Vault and Microsoft Entra ID role-based access.
![image](https://github.com/Shashi42/Azure-End-to-End-Sales-Data-Analytics-Pipeline/assets/26250463/d28f9c77-0027-4bb5-96f4-104109346f82)



## End Notes

* This project provides a great overview to many of Azure services such as Azure Data Factory, Azure Databricks, Azure Synapse Analytics.

* Implemented basic data quality checks in Databricks notebooks (null handling, schema validation) before loading into Silver/Gold layers.

* Added custom KPI metrics in Power BI such as regional sales growth and product profitability.

* Another thing to note is that, project couldve been made smaller using only Azure Data factory but I added Databricks and Synapse Analytics to explore what these have to offer.

