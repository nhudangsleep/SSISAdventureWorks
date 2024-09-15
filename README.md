# SSISAdventureWorks

## Objectives
This project aims to create an environment where needed data to perform sales performance such as data about customers, products, and locations are stored in a data warehouse. Also, to facilitate the process of decision-making, the following tasks should be conducted as the target of this project:
- A data warehouse
- A multidimensional cube
- Valuable information about sales performance

## Data & Tools
Adventure Works Cycles (AWC) database (specifically AdventureWorks 2019) will be used in this project as a use case. This database will be divided into many source types in order to address the multi-source data management challenges.

Tools used in this project:
- Visual Studio
- SQL Server Management Studio (SSMS)

## What we did
### 1. Overall Process
To create a data warehouse, we must first have some data to store in the warehouse. Sooo, here comes the ingestion process for each type of data source:
- Database: Get fully loaded for the first time, then incremental loaded
- Other file types (.tsv, .xlsx, .xml, etc.): Get ingested into the staging area and organized into the appropriate folder

These data will then go through the ETL (Extract, Transform, Load) process and are stored in the data warehouse. After that, an OLAP cube will be created to serve the multidimensional analysis.

### 2. Data Modeling
The next step is to identify which data is going to serve as a fact or a dimensional table. For this project, we conducted the data modeling process following a snowflake schema and identified 01 fact and 07 dimension tables, which are: DimLocation, DimTerritory, DimCustomer, DimProduct, DimCategory, DimSubcategory, DimTime, and FactSales.

### 3. ETL
#### Data Staging Area
Here, we use a foreach loop to iterate through all file names without having to manually classify them. Within this loop, the 'Execute SQL Command' component is utilized to verify the
loading status of each file. Once confirmed, the data flow is triggered to load the respective file into the designated table. Simultaneously, vital information, specifically the file name, is logged into the tbl_logs table. 

#### Data Warehouse
The ETL process for our data warehouse consists of these steps:
- Extract data
- Join relevant tables
- Transform & map data columns
- Track historical with slowly changing dimension type 2 (SCD) logic
- Load data to destinated (dimensional/fact) tables

By then, our data warehouse is perfectly formed and ready for analysis.

#### OLAP Cube
Here, we also do an additional step, which is creating an OLAP cube. This cube is used to perform multidimensional analysis, hence will further facilitate AWC in understanding their sales performance in-depth for better decision-making.

For more information, please refer to *231MI4201_LiveLaughLove.pdf* in Document.
