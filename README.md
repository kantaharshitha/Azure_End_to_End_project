
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

![Data_bricks](Data_bricks.PNG)

![Data_lake](Data_lake.PNG)

3.DATA LOADING: Data from DataLakeGen2 (transformed data Gold) is connected with Power BI using Synapse Analytics and also stored data in Serverless SQL database in Synapse.

![Synapse_analytics](Synapse_analytics.PNG)


4.DATA GOVERANCE AND SECURITY:Using Azure key vault we stored confidential data in keys and Azure Active Directory we managed the access for different actions in project.

![Key_vault](Key_vault.PNG)


5.DATA REPORTING:Power BI is connected to synapse Analytics and created a dyanmic dashboard and also done required transformations in Powerquery for the report

![Power_BI](Power_BI.PNG)

6.PIPELINE TESTING:In this phase we update the on premise data base manually and check pipeline is exceuted and dashboard is updated or not



Technologies Used:

Data Source: SQL Server

Orchestration: Azure Data Factory

Ingestion: Azure Data Lake Gen2

Transformation: Azure DataBricks

Storage: Azure Synapse Analytics

Authentication and Secrets Management: Azure Active Directory and Azure Key Vault

Data Visualization: PowerBI










