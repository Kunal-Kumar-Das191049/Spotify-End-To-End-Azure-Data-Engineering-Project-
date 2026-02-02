# Spotify-End-To-End-Azure-Data-Engineering-Project-
## Tech Stacks used
##### Azure Cloud
##### Azure Data Factory
##### Azure Databricks
##### Azure SQL Database
##### Unity Catalog
##### Delta Live Tables
##### Spark Streaming
##### Pyspark
##### Databricks Asset Bundles
##### Logic Apps
##### Medallion Architecture
##### GitHub
##### CI/CD



#### Azure Data Factory Tutorial
#### Azure SQL DB Source
#### Incremental Ingestion Pipelines With Data Factory
#### Adding Backfilling Feature In The Pipelines
#### Looping The Pipelines
#### Logic Apps With Azure Data Factory
#### Azure Databricks Tutorial
#### Databricks Unity Catalog Tutorial
#### Spark Streaming With Databricks Autoloader
#### Python Utilities 
#### PySpark Transformations & APIs
#### Metadata Driven Pipelines With PySpark and Jinja2
#### Star Schema and Slowly Changing Dimensions
#### Databricks Delta Live Tables Tutorial
#### Databricks Incremental Data Load
#### Databricks Asset Bundles For CI/CD


## Project Features:
##### Incremental Processing
##### Backfilling Enabled
##### Stream Processing
##### Custom Utilities
##### Metadata Driven Code
##### Star Schema
##### Git CI/CD Standards
##### Dynamic Code





## Project Architecture
![WhatsApp Image 2026-01-29 at 6 55 12 AM](https://github.com/user-attachments/assets/cd186220-e56f-49a3-87ab-c4683a15a04a)


This project includes Data ingestion using Azure Data factory where I have build realtime dynamic pipeline with backfilling capabilities. I have used Azure Databricks and Spark structured streaming and Autoloader for Big data processing within Python utilities. I have build slowly changing dimensions and star schema using DLT and lakeflow pipelines. I have also used Databricks Asset Bundles to Push and deploy my code to GitHub.  


SQL DB and GitHub(for static files) is our data sources. I have used the Azure Data Factory to load the data into the Bronze(Raw) layer. In the Bronze layer, I have Dynamically load the data incrementally using Incremental data load, backfilling of Data in the pipeline. I have also used the Git CI/CD to collaborate using git branches. 

In the Silver layer, I have used Azure Databricks to use and process the data sitting in the bronze layer. I have created Unity catalog, Unity metastore, Credentials, external locations, Security and Groups. I have also used the spark structured streaming using Autoloader. Also build the Star Schema and slowly changing dimensions. I have also build the metadata driven pipeline With PySpark and Jinja2(templating library)

In the Gold layer, I have build the final model using Databricks Delta Live Tables.
I have also used the Databricks Asset Bundles For CI/CD

At the End, I have build the warehouse to share the endpoints with the development team.




## Azure cloud
### Resources used in the project
##### Access Connector for Azure Databricks
##### Databriks
##### Data Factory
##### Logic Apps
##### Azure SQL Database
##### Azure SQL Server
##### Azure Data Lake Storage(ADLS) Gen2
##### API Connection - Outlook

<img width="1920" height="769" alt="Azure Cloud Resource Group" src="https://github.com/user-attachments/assets/d34854c1-795d-4f98-aa90-f0bf7744193d" />


Bronze Layer Folders
<img width="1920" height="601" alt="Bronze Layer Folders" src="https://github.com/user-attachments/assets/fc7bf3fc-227a-493c-b41c-aef9676a1ca1" />



## Azure Data Factory
Git configuration with Azure Data Factory 
<img width="1920" height="768" alt="Git Configuration with ADF" src="https://github.com/user-attachments/assets/9dcbbb96-3d29-4035-9608-c2a0c0579af3" />

Linked Services for connecting ADF with SQL database and ADLS
<img width="1920" height="817" alt="Connecting ADF with SQL database and ADLS" src="https://github.com/user-attachments/assets/428c0c02-21da-4e5e-bd2f-1ea456dc0c2e" />

Dynamic pipeline to incrementally load the raw data from SQL Database to ADLS(Bronze Layer)
<img width="1920" height="721" alt="Pipeline for Incrementally Load the raw data from SQL database to ADLS(Bronze Layer)" src="https://github.com/user-attachments/assets/62aed14f-5fae-406c-93ff-9fe9f55f79f7" />
### Features of the pipeline
##### Incremental Ingestion
##### Backfilling Feature
Here I have created 3 datasets:	
##### 1. azure sql - To define the location of data present in SQL Database 
##### 2. json_dynamic - To dynamically define the location of json data present in ADLS
##### 3. parquet_dynamic - To dynamically define the location of parquet file format data present in ADLS

Parameter used in the pipeline
<img width="1920" height="714" alt="Parameters used in the pipeline - incremental_ingestion" src="https://github.com/user-attachments/assets/c9022fcc-1912-447a-a219-91d7ee4f7251" />

Variable used in the pipeline
<img width="1920" height="720" alt="Variables used in the pipeline - incremental_ingestion" src="https://github.com/user-attachments/assets/a8974e04-08d9-4b61-8994-0a8021821fef" />

Colone of same Pipeline with Loop and Alerts (By using Logic App) 
<img width="1920" height="831" alt="Pipeline for Incrementally Load the raw data from SQL database to ADLS(Bronze Layer) using Loop" src="https://github.com/user-attachments/assets/f7a647a1-3712-4910-801d-5264b054a53d" />

Parameter used in the pipeline
<img width="1920" height="832" alt="Parameter used in the pipeline - incremental_loop" src="https://github.com/user-attachments/assets/1c725b7c-5d2e-4a6f-a190-ad3b5cf2a431" />

Variable used in the pipeline
<img width="1920" height="833" alt="Variables used in the pipeline - incremental_loop" src="https://github.com/user-attachments/assets/8f3b4212-e845-452d-938c-2648f29295d5" />

## Logic Apps
I have used it for sending notifications via Outlook when pipeline failed.
<img width="1920" height="820" alt="Logic app designer Page" src="https://github.com/user-attachments/assets/37288adf-9c0b-4f7f-b9c2-97f8ea8de3cf" />

Logic app - Setting the trigger - When an HTTP request is received
<img width="1920" height="824" alt="Logic app - Setting the activity - When an HTTP request is received" src="https://github.com/user-attachments/assets/331dc540-4a66-4ade-a7e6-fc8a825f39fc" />

Logic app - Setting the action - Send an Email(V2)
<img width="1883" height="818" alt="Logic app - Setting the action - Send an Email(V2) " src="https://github.com/user-attachments/assets/f93104b8-ff92-468a-b96c-cc38197dd240" />


















