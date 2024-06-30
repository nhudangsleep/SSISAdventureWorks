# SSISAdventureWorks

## Objectives
This project aims to create an environment where needed data to perform sales performance such as data about customers, products, and locations are stored in a data warehouse. Also, to facilitate the process of decision-making, the following tasks should be conducted as the target of this project:
- A data warehouse;
- A multidimensional cube;
- Valuable information about sales performance.

## Data
Adventure Works Cycles (AWC) database (specifically AdventureWorks 2019) will be used in this project as a use case. This database will be divided into many source types in order to address the multi-source data management challenges.

## Tools
- Visual Studio
- SQL Server Management Studio (SSMS)

## What we did
### Data Ingestion (?) // Overall Process
To create a data warehouse, we must first have some data to store in the warehouse. Sooo, here comes the ingestion process for each type of data source:
- Database: Get full loaded for the first time, then incremental loaded;
- Other file types (.tsv, .xlsx, .xml, etc.): Get ingested into the staging area and organized into the appropriate folder.

### Data Modeling
The next step is to identify which data is going to serve as a fact or a dimensional table. For this project, we conducted the data modeling process following a snowflake schema and identified 1 fact and 7 dimensional tables, which are: DimLocation, DimTerritory, DimCustomer, DimProduct, DimCategory, DimSubcategory, DimTime, and FactSales.

### ETL
#### Data Staging Area
