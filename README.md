# 🎧 Spotify End-To-End Azure Data Engineering Project
## 📌 Project Overview

This project demonstrates a **complete end-to-end Data Engineering pipeline** built on **Microsoft Azure + Databricks ecosystem** using **Medallion Architecture (Bronze → Silver → Gold)**.

The pipeline ingests data from **Azure SQL Database & GitHub**, processes it using **Azure Data Factory**, transforms and models data using **Databricks & Delta Live Tables**, and finally exposes curated datasets through a **Data Warehouse layer**.

## 🧰 Tech Stack

### ☁️ Cloud & Storage
- Azure Cloud
- Azure Data Lake Storage (ADLS Gen2)

### 🔄 Data Ingestion & Orchestration
- Azure Data Factory
- Logic Apps
- Incremental Pipelines
- Backfilling Pipelines
- Loop-based Dynamic Pipelines

### ⚡ Data Processing
- Azure Databricks
- Spark Structured Streaming
- Databricks Autoloader
- PySpark
- Python Utilities
- Metadata Driven Pipelines (Jinja2)

### 🧱 Data Modeling
- Unity Catalog
- Star Schema
- Slowly Changing Dimensions (SCD Type 2)
- Delta Live Tables (DLT)

### 🚀 DevOps & CI/CD
- GitHub
- Databricks Asset Bundles
- Git Branch Collaboration


## ✨ Project Features

- ✅ Incremental Data Processing
- ✅ Backfilling Support
- ✅ Real-time Stream Processing
- ✅ Metadata Driven Code
- ✅ Dynamic Pipeline Execution
- ✅ Star Schema Data Modeling
- ✅ CI/CD Integration
- ✅ Custom PySpark Utilities




## Project Architecture
![WhatsApp Image 2026-01-29 at 6 55 12 AM](https://github.com/user-attachments/assets/cd186220-e56f-49a3-87ab-c4683a15a04a)


This project includes Data ingestion using Azure Data factory where I have build realtime dynamic pipeline with backfilling capabilities. I have used Azure Databricks and Spark structured streaming and Autoloader for Big data processing within Python utilities. I have build slowly changing dimensions and star schema using DLT and lakeflow pipelines. I have also used Databricks Asset Bundles to Push and deploy my code to GitHub.  


## 📊 Data Flow Explanation

### 🔹 Data Sources
- Azure SQL Database
- GitHub (Static Files)



### 🥉 Bronze Layer (Raw Data)

👉 Implemented using **Azure Data Factory**

- Incremental ingestion from SQL Database
- Backfilling support
- Dynamic pipeline execution
- CDC-based loading
- Stored data in ADLS in Parquet format



### 🥈 Silver Layer (Cleaned & Transformed Data)

👉 Implemented using **Azure Databricks**

- Unity Catalog & Metastore configuration
- External locations & credential setup
- Spark Structured Streaming using Autoloader
- PySpark transformations
- Metadata-driven joins using Jinja2



### 🥇 Gold Layer (Business Ready Data)

👉 Implemented using **Delta Live Tables**

- Star Schema implementation
- SCD Type 2 implementation
- Final curated datasets



### 🏬 Warehouse Layer

- Exposes analytical datasets
- Provides endpoints for downstream applications

---




# ☁️ Azure Infrastructure Setup

## 🔹 Resources Used

- Access Connector for Azure Databricks
- Azure Databricks
- Azure Data Factory
- Logic Apps
- Azure SQL Database
- Azure SQL Server
- Azure Data Lake Storage(ADLS) Gen2
- Outlook API Connection

---

## 🧾 Resource Group

![Azure Resource Group](https://github.com/user-attachments/assets/d34854c1-795d-4f98-aa90-f0bf7744193d)

---

# 🗄️ Storage Layer (ADLS Gen2)

## Containers
![ADLS Containers](https://github.com/user-attachments/assets/7a5afc52-2220-44b3-b8a7-385e428cc729)

## Bronze Layer Structure
![Bronze Layer](https://github.com/user-attachments/assets/fc7bf3fc-227a-493c-b41c-aef9676a1ca1)

---

# 🔄 Azure Data Factory Implementation
## Git configuration with Azure Data Factory 
<img width="1920" height="768" alt="Git Configuration with ADF" src="https://github.com/user-attachments/assets/9dcbbb96-3d29-4035-9608-c2a0c0579af3" />

## Linked Services for connecting ADF with SQL database and ADLS
<img width="1920" height="817" alt="Connecting ADF with SQL database and ADLS" src="https://github.com/user-attachments/assets/428c0c02-21da-4e5e-bd2f-1ea456dc0c2e" />

---
## Dynamic pipeline to incrementally load the raw data from SQL Database to ADLS(Bronze Layer)
<img width="1920" height="721" alt="Pipeline for Incrementally Load the raw data from SQL database to ADLS(Bronze Layer)" src="https://github.com/user-attachments/assets/62aed14f-5fae-406c-93ff-9fe9f55f79f7" />

### Pipeline Features
- Incremental Loading
- Backfilling Support
- 
### Datasets Used:	
1. azure sql - To define the location of data present in SQL Database
2. json_dynamic - To dynamically define the location of json data present in ADLS
3. parquet_dynamic - To dynamically define the location of parquet file format data present in ADLS

### Pipeline Parameters
<img width="1920" height="714" alt="Parameters used in the pipeline - incremental_ingestion" src="https://github.com/user-attachments/assets/c9022fcc-1912-447a-a219-91d7ee4f7251" />

### Pipeline Variables
<img width="1920" height="720" alt="Variables used in the pipeline - incremental_ingestion" src="https://github.com/user-attachments/assets/a8974e04-08d9-4b61-8994-0a8021821fef" />

---

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

## Databricks
Databricks Overview dashboard
<img width="1920" height="824" alt="Databricks Dashboard" src="https://github.com/user-attachments/assets/55dd3277-e1ed-4dec-9503-be81838b9974" />

Access connector for Azure Databricks Overview dashboard
<img width="1920" height="817" alt="Access connector for databricks dashboard" src="https://github.com/user-attachments/assets/ae712b45-f22b-4010-b1e9-1d76a9ebfca0" />

In ADLS I have added a role assignment (Storage Blob Data contributor) to the managed Identity ("AccessConnectorForDatabricks_SpotifyProject"). So that databricks can access the ADLS data with this access connector.
<img width="1920" height="837" alt="Storage Blob data contributor role assignment to databricks access connector" src="https://github.com/user-attachments/assets/761e2f74-151e-467a-a31f-4f28fc637791" />

Created a dedicated container named "databricksmetastore" in ADLS
<img width="1920" height="555" alt="ADLS containers" src="https://github.com/user-attachments/assets/2af897a6-8bc8-43f1-9f16-f39bc5eccab9" />

Deleted the default metastore and created a new metastore
<img width="1920" height="822" alt="New Metstore Created" src="https://github.com/user-attachments/assets/70d685d4-8c3c-4104-99cf-bc028817a622" />

Workspace associated to the metastore
<img width="1920" height="839" alt="Assigned workspace to the new metastore" src="https://github.com/user-attachments/assets/081d1180-7c71-40e6-b43b-38e64607ab30" />

Catalog creation in Databricks workspace
<img width="1920" height="822" alt="catalog creation in databricks workspace" src="https://github.com/user-attachments/assets/b339af2f-66f2-4a70-89e7-8a908976c30e" />

Created a credential and external locations for ADLS bronze, Silver and Gold layer.
<img width="1920" height="834" alt="Credential creation" src="https://github.com/user-attachments/assets/023dc398-149a-49af-aa93-1f5e229bea7f" />
<img width="1920" height="824" alt="External Locations" src="https://github.com/user-attachments/assets/d4b001f0-3d4d-4382-a7dd-44efb9952ef2" />

Created Databricks Asset Bundle
<img width="1920" height="827" alt="Databricks Asset Bundle" src="https://github.com/user-attachments/assets/6c04041b-4690-431f-8749-0c9a95c6d3a9" />

Created a notebook - Used Autoloader to load the data in Stream and pyspark transformations to transform the data
<img width="1920" height="828" alt="Pyspark transformation - 1" src="https://github.com/user-attachments/assets/d9b4c604-1da1-4224-8d9f-84b91bec24b4" />

<img width="1920" height="823" alt="Pyspark transformation - 2" src="https://github.com/user-attachments/assets/3371dcb5-9111-49ab-936e-75b526c5fcf0" />

<img width="1920" height="831" alt="Pyspark transformation - 3" src="https://github.com/user-attachments/assets/dbef3434-b4ec-428e-a112-fec1cc6f83fe" />

<img width="1920" height="809" alt="Pyspark transformation - 4" src="https://github.com/user-attachments/assets/4c87fad0-37bf-4faf-bd45-1761423b14ae" />

<img width="1920" height="845" alt="Pyspark transformation - 5" src="https://github.com/user-attachments/assets/ba4219d0-7097-4315-8da7-26d07839a024" />

<img width="1920" height="826" alt="Pyspark transformation - 6" src="https://github.com/user-attachments/assets/31f2f16c-5ccd-4e23-b86f-a265059d0791" />

<img width="1920" height="824" alt="Pyspark transformation - 7" src="https://github.com/user-attachments/assets/4bc0b5cb-eb53-4fe3-9d12-9c252ded653c" />

<img width="1920" height="832" alt="Pyspark transformation - 8" src="https://github.com/user-attachments/assets/989d9db5-e0e0-4a2f-8df6-6b9f5c4c2b78" />

<img width="1920" height="830" alt="Pyspark transformation - 9" src="https://github.com/user-attachments/assets/f1f35538-3503-42b9-973f-cc86db716aee" />

<img width="1920" height="817" alt="Pyspark transformation - 10" src="https://github.com/user-attachments/assets/e9a746b7-b835-4bb4-a296-e7a07e3afd69" />

<img width="1920" height="810" alt="Pyspark transformation - 11" src="https://github.com/user-attachments/assets/81089915-acc5-4a7a-843b-ebef87c8d33e" />

Created a Utility File to create a reusable method to delete columns
<img width="1920" height="824" alt="Reusable method for deleting columns " src="https://github.com/user-attachments/assets/237620c4-f54f-4d4f-9c61-423c805cd1b4" />

written the processed table in the databricks catalog inside silver schema.
<img width="1920" height="815" alt="Catalog - Silver Schema - Tables" src="https://github.com/user-attachments/assets/c96eac50-dd89-4d48-90f0-5fa57b1ff04e" />

created another notebook named "jinja_notebook" and used Jinja to dynamically apply joins between FactStream table , dimuser table and dimtrack table present in the databricks Unity catalog in Silver Schema.
<img width="1920" height="837" alt="Jinja -1" src="https://github.com/user-attachments/assets/96e0b652-160d-4795-a406-6791fad8ab8a" />

<img width="1920" height="841" alt="jinja - 2" src="https://github.com/user-attachments/assets/70fc489b-d838-4346-8e6b-27d40de1dcc2" />

<img width="1920" height="824" alt="jinja - 3" src="https://github.com/user-attachments/assets/18ee48b0-a578-4b4d-8f87-a0f4b8f2b891" />

<img width="1920" height="818" alt="Jinja - 4" src="https://github.com/user-attachments/assets/802d1c3d-8872-486f-adfd-c509fb668f5e" />

<img width="1920" height="829" alt="Jinja 5" src="https://github.com/user-attachments/assets/4da88cf8-cc16-4300-bb63-346bf87b9537" />

Created a new ETL pipeline in databricks using DLT for creating star schema and slowly changing dimension
<img width="1920" height="833" alt="ETL Pipeline using DLT 1" src="https://github.com/user-attachments/assets/cf22aaf5-f14b-4667-a8fd-51d55079b803" />

<img width="1920" height="813" alt="ETL Pipeline using DLT 2" src="https://github.com/user-attachments/assets/ea3a1e40-caae-4662-afd9-4acbacdcdb2a" />

<img width="1920" height="828" alt="ETL Pipeline using DLT 3" src="https://github.com/user-attachments/assets/9066f651-baad-4738-a1b4-7982cf1ed2e8" />

<img width="1920" height="834" alt="ETL Pipeline using DLT 4" src="https://github.com/user-attachments/assets/e663daaa-46c4-4094-89f0-4cacf0b49ac7" />

<img width="1920" height="828" alt="ETL Pipeline using DLT 5" src="https://github.com/user-attachments/assets/346d3486-86ea-46ee-bac0-dfec75acbc05" />

DAG for the ETL Pipeline 
<img width="1545" height="905" alt="DAG for Gold Pipeline" src="https://github.com/user-attachments/assets/28f6e89b-c3ab-48a9-b0b2-e66cc5f76783" />

SCD Type 2 Successfully implemented in the gold layer data
<img width="1636" height="907" alt="SCD Type 2 Successfully Implemented" src="https://github.com/user-attachments/assets/3949bb13-4b01-4cee-bb49-72674362d172" />

All tables has successfully transferred to the Gold schema in the catalog
<img width="1920" height="830" alt="Gold layer schema tables " src="https://github.com/user-attachments/assets/f8baeaa9-60ac-40fb-83f6-7217d5ed549b" />

Deployed the asset bundle in the dev environment and it created.bundle
databricks.yml
<img width="1920" height="818" alt="databricks yml file" src="https://github.com/user-attachments/assets/4ecbbd1a-6dd3-4fe3-8e80-462c6c25b2da" />

<img width="1920" height="822" alt="bundle file" src="https://github.com/user-attachments/assets/cb8a32db-17ea-4825-a2af-f1834d789af6" />


# 🎧 Spotify End-To-End Azure Data Engineering Project

---

## 📌 Project Overview

This project demonstrates a **complete end-to-end Data Engineering pipeline** built on **Microsoft Azure + Databricks ecosystem** using **Medallion Architecture (Bronze → Silver → Gold)**.

The pipeline ingests data from **Azure SQL Database & GitHub**, processes it using **Azure Data Factory**, transforms and models data using **Databricks & Delta Live Tables**, and finally exposes curated datasets through a **Data Warehouse layer**.

---

## 🧰 Tech Stack

### ☁️ Cloud & Storage
- Azure Cloud
- Azure Data Lake Storage (ADLS Gen2)

### 🔄 Data Ingestion & Orchestration
- Azure Data Factory
- Logic Apps
- Incremental Pipelines
- Backfilling Pipelines
- Loop-based Dynamic Pipelines

### ⚡ Data Processing
- Azure Databricks
- Spark Structured Streaming
- Databricks Autoloader
- PySpark
- Python Utilities
- Metadata Driven Pipelines (Jinja2)

### 🧱 Data Modeling
- Unity Catalog
- Star Schema
- Slowly Changing Dimensions (SCD Type 2)
- Delta Live Tables (DLT)

### 🚀 DevOps & CI/CD
- GitHub
- Databricks Asset Bundles
- Git Branch Collaboration

---

## ✨ Project Features

- ✅ Incremental Data Processing
- ✅ Backfilling Support
- ✅ Real-time Stream Processing
- ✅ Metadata Driven Code
- ✅ Dynamic Pipeline Execution
- ✅ Star Schema Data Modeling
- ✅ CI/CD Integration
- ✅ Custom PySpark Utilities

---

## 🏗️ Project Architecture

![Architecture](https://github.com/user-attachments/assets/cd186220-e56f-49a3-87ab-c4683a15a04a)

---

## 📊 Data Flow Explanation

### 🔹 Data Sources
- Azure SQL Database
- GitHub (Static Files)

---

### 🥉 Bronze Layer (Raw Data)

👉 Implemented using **Azure Data Factory**

- Incremental ingestion from SQL Database
- Backfilling support
- Dynamic pipeline execution
- CDC-based loading
- Stored data in ADLS in Parquet format

---

### 🥈 Silver Layer (Cleaned & Transformed Data)

👉 Implemented using **Azure Databricks**

- Unity Catalog & Metastore configuration
- External locations & credential setup
- Spark Structured Streaming using Autoloader
- PySpark transformations
- Metadata-driven joins using Jinja2

---

### 🥇 Gold Layer (Business Ready Data)

👉 Implemented using **Delta Live Tables**

- Star Schema implementation
- SCD Type 2 implementation
- Final curated datasets

---

### 🏬 Warehouse Layer

- Exposes analytical datasets
- Provides endpoints for downstream applications

---

# ☁️ Azure Infrastructure Setup

## 🔹 Resources Used

- Azure Databricks
- Azure Data Factory
- Azure SQL Database
- Azure SQL Server
- Azure ADLS Gen2
- Logic Apps
- Databricks Access Connector
- Outlook API Connection

---

## 🧾 Resource Group

![Azure Resource Group](https://github.com/user-attachments/assets/d34854c1-795d-4f98-aa90-f0bf7744193d)

---

# 🗄️ Storage Layer (ADLS Gen2)

## Containers
![ADLS Containers](https://github.com/user-attachments/assets/7a5afc52-2220-44b3-b8a7-385e428cc729)

## Bronze Layer Structure
![Bronze Layer](https://github.com/user-attachments/assets/fc7bf3fc-227a-493c-b41c-aef9676a1ca1)

---

# 🔄 Azure Data Factory Implementation

## Git Integration
![ADF Git Integration](https://github.com/user-attachments/assets/9dcbbb96-3d29-4035-9608-c2a0c0579af3)

---

## Linked Services
![ADF Linked Services](https://github.com/user-attachments/assets/428c0c02-21da-4e5e-bd2f-1ea456dc0c2e)

---

## 📥 Incremental Ingestion Pipeline

![Incremental Pipeline](https://github.com/user-attachments/assets/62aed14f-5fae-406c-93ff-9fe9f55f79f7)

### Pipeline Features
- Incremental Loading
- Backfilling Support

### Datasets Used
1. Azure SQL Dataset
2. JSON Dynamic Dataset
3. Parquet Dynamic Dataset

---

### Pipeline Parameters
![Pipeline Parameters](https://github.com/user-attachments/assets/c9022fcc-1912-447a-a219-91d7ee4f7251)

### Pipeline Variables
![Pipeline Variables](https://github.com/user-attachments/assets/a8974e04-08d9-4b61-8994-0a8021821fef)

---

## 🔁 Loop-Based Dynamic Pipeline + Alerts

![Loop Pipeline](https://github.com/user-attachments/assets/f7a647a1-3712-4910-801d-5264b054a53d)

### Parameters
![Loop Parameters](https://github.com/user-attachments/assets/1c725b7c-5d2e-4a6f-a190-ad3b5cf2a431)

### Variables
![Loop Variables](https://github.com/user-attachments/assets/8f3b4212-e845-452d-938c-2648f29295d5)

---

# 📧 Logic Apps Integration

Used for sending **failure notifications via Outlook**

### Designer View
![Logic App Designer](https://github.com/user-attachments/assets/37288adf-9c0b-4f7f-b9c2-97f8ea8de3cf)

### HTTP Trigger
![Logic Trigger](https://github.com/user-attachments/assets/331dc540-4a66-4ade-a7e6-fc8a825f39fc)

### Email Action
![Logic Email](https://github.com/user-attachments/assets/f93104b8-ff92-468a-b96c-cc38197dd240)

---

# ⚡ Databricks Implementation

## Workspace Overview
![Databricks Dashboard](https://github.com/user-attachments/assets/55dd3277-e1ed-4dec-9503-be81838b9974)

---

## Access Connector Configuration
![Access Connector](https://github.com/user-attachments/assets/ae712b45-f22b-4010-b1e9-1d76a9ebfca0)

---

## Role Assignment
![Role Assignment](https://github.com/user-attachments/assets/761e2f74-151e-467a-a31f-4f28fc637791)

---

## Unity Catalog Setup

### Metastore Creation
![Metastore](https://github.com/user-attachments/assets/70d685d4-8c3c-4104-99cf-bc028817a622)

### Workspace Assignment
![Workspace Mapping](https://github.com/user-attachments/assets/081d1180-7c71-40e6-b43b-38e64607ab30)

### Catalog Creation
![Catalog](https://github.com/user-attachments/assets/b339af2f-66f2-4a70-89e7-8a908976c30e)

---

## External Locations & Credentials
![Credentials](https://github.com/user-attachments/assets/023dc398-149a-49af-aa93-1f5e229bea7f)
![External Locations](https://github.com/user-attachments/assets/d4b001f0-3d4d-4382-a7dd-44efb9952ef2)

---

# 🔄 Streaming & Transformations

## Autoloader + PySpark Transformations
(Streaming Bronze → Silver)

![Transformation 1](https://github.com/user-attachments/assets/d9b4c604-1da1-4224-8d9f-84b91bec24b4)

![Transformation 2](https://github.com/user-attachments/assets/3371dcb5-9111-49ab-936e-75b526c5fcf0)

![Transformation 3](https://github.com/user-attachments/assets/dbef3434-b4ec-428e-a112-fec1cc6f83fe)

---

## Custom Utility Functions
![Utility File](https://github.com/user-attachments/assets/237620c4-f54f-4d4f-9c61-423c805cd1b4)

---

## Silver Layer Tables
![Silver Tables](https://github.com/user-attachments/assets/c96eac50-dd89-4d48-90f0-5fa57b1ff04e)

---

# 🧠 Metadata Driven Pipelines (Jinja2)

Dynamic joins between Fact & Dimension tables

![Jinja 1](https://github.com/user-attachments/assets/96e0b652-160d-4795-a406-6791fad8ab8a)

![Jinja 2](https://github.com/user-attachments/assets/70fc489b-d838-4346-8e6b-27d40de1dcc2)

---

# 🥇 Gold Layer Implementation (DLT)

## Star Schema + SCD Type 2

![DLT Pipeline](https://github.com/user-attachments/assets/cf22aaf5-f14b-4667-a8fd-51d55079b803)

---

## DAG View
![DLT DAG](https://github.com/user-attachments/assets/28f6e89b-c3ab-48a9-b0b2-e66cc5f76783)

---

## SCD Type 2 Output
![SCD Type 2](https://github.com/user-attachments/assets/3949bb13-4b01-4cee-bb49-72674362d172)

---

## Gold Schema Tables
![Gold Tables](https://github.com/user-attachments/assets/f8baeaa9-60ac-40fb-83f6-7217d5ed549b)

---

# 🚀 CI/CD Using Databricks Asset Bundles

![Asset Bundle](https://github.com/user-attachments/assets/6c04041b-4690-431f-8749-0c9a95c6d3a9)

### Bundle Configuration
![Databricks YAML](https://github.com/user-attachments/assets/4ecbbd1a-6dd3-4fe3-8e80-462c6c25b2da)

![Bundle Deployment](https://github.com/user-attachments/assets/cb8a32db-17ea-4825-a2af-f1834d789af6)

---

# 🎯 Final Outcome

- Fully automated Azure Data Engineering pipeline
- Real-time streaming ingestion
- Enterprise-grade medallion architecture
- Production-ready CI/CD implementation
- Scalable metadata-driven framework

---

# 👨‍💻 Author

**Kunal Kumar Das**
































































