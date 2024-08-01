# End-to-End Azure Data Engineering Project
![overview](https://github.com/SardarBoy/AzureDataEngineering1/blob/80604db716f778381552bb1dd901dd997ac0e52f/Project%20Overview.png)

This project demonstrates a real-world application of data engineering using Microsoft Azure. The goal was to create a data pipeline that migrates data from an on-premises SQL Server database to the cloud. The pipeline is designed to run daily, triggered by the addition of new data to the database.

## Components Used

1. **On-Premises SQL Server Database**
   - The project began with data stored in our local SQL Server database.

2. **Azure Data Factory (ADF)**
   - ADF served as the ETL tool for data ingestion, connecting to the SQL Server to copy the necessary tables to the cloud.

3. **Azure Data Lake Storage Gen2**
   - This was the storage destination for all ingested data.

4. **Azure Databricks**
   - Used for transforming the data into the required format.

5. **Azure Synapse Analytics**
   - This platform loaded the transformed data into the Azure SQL database.

6. **Power BI**
   - Utilized to pull data from Azure Synapse Analytics and create business-use reports.

7. **Azure Active Directory and Azure Key Vault**
   - Implemented to enhance security and manage access to data within the cloud environment.




![resourcegroup](https://github.com/SardarBoy/AzureDataEngineering1/blob/73438a92dbf7c0bc03c336ffef31c0eae08119be/ResourceGroup.png)

![pipeline](https://github.com/SardarBoy/AzureDataEngineering1/blob/73438a92dbf7c0bc03c336ffef31c0eae08119be/Pipeline.png)


![dashboard](https://github.com/SardarBoy/AzureDataEngineering1/blob/44233eb41ef8e66c9bde77e4d7a0ac6710719e83/Dashboard.png)
