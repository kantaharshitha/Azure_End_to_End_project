
# END TO END SERVER TO CLOUD MIGRATION 

TThis END to END project demonstrates on premise Adventure Work sales local database to the cloud and culminating in Power BI reporting, all automated.

# OBJECTIVE:
To seamlessly migrate our existing local server infrastructure to the cloud while ensuring that any updates made to the local server are reflected in our Power BI Reports connected to the cloud, thus ensuring data consistency, accessibility, and scalability across our organization's digital ecosystem.

# PREREQUISITES:
 Download Microsoft SQL server and AdventureWork database
 
 Create Azure Account and in Resource Group create Resources (Azure DataLakeGen2,Azure Key Vault,Azure Synapse Analytics,Azure DataBricks, Azure Data Factory) 

 Create Selfhosted Integration RunTime to Connect with SQL server

 Download JavaRuntime Environment

 PowerBI

# WORKFLOW

1.DATA EXTRACTION: Here We connect SQl server to azure data factory(using self hosted Integration RunTime) and create a pipeline to extract data and store in bronze folder in DataLakeGen2 Storage.

![Extraction_pipeline](https://github.com/kantaharshitha/Azure_End_to_End_project/assets/55930087/41ddd8a7-5fbe-49a9-92f8-c0027d57e53a)

2.DATA TRANSFORMATION: Here we have done Transformations in Azure DataBricks and created 3 notebooks to store data in medallion data lake architecture (bronze, silver, gold).

![Data_bricks](https://github.com/kantaharshitha/Azure_End_to_End_project/assets/55930087/c1699fcd-4dde-42f1-8f94-4526b140e88a)

![Data_lake](https://github.com/kantaharshitha/Azure_End_to_End_project/assets/55930087/486dc8fe-8626-496f-b743-394845e9b4ea)


3.DATA LOADING: Data from DataLakeGen2 (transformed data Gold) is connected with Power BI using Synapse Analytics and also stored data in Serverless SQL database in Synapse.

![Synapse_analytics](https://github.com/kantaharshitha/Azure_End_to_End_project/assets/55930087/6d31e7d7-ca72-4455-9b18-6ef183e907ca)


4.DATA GOVERANCE AND SECURITY:Using Azure key vault we stored confidential data in keys and Azure Active Directory we managed the access for different actions in project.

![Key_vault](https://github.com/kantaharshitha/Azure_End_to_End_project/assets/55930087/036186bb-326d-4938-b70d-5fd855d2f5a0)


5.DATA REPORTING:Power BI is connected to synapse Analytics and created a dyanmic dashboard and also done required transformations in Powerquery for the report

![Power_BI](https://github.com/kantaharshitha/Azure_End_to_End_project/assets/55930087/f95948b5-b201-4170-bfc7-1808672d4203)


6.PIPELINE TESTING:In this phase we update the on premise data base manually and check pipeline is exceuted and dashboard is updated or not

![Presentation1](https://github.com/kantaharshitha/Azure_End_to_End_project/assets/55930087/0925092e-eedc-457b-9522-56232f9770aa)


Technologies Used:

Data Source: SQL Server

Orchestration: Azure Data Factory

Ingestion: Azure Data Lake Gen2

Transformation: Azure DataBricks

Storage: Azure Synapse Analytics

Authentication and Secrets Management: Azure Active Directory and Azure Key Vault

Data Visualization: PowerBI










