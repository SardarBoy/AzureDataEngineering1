# End-to-End Azure Data Engineering Project
This project demonstrates a real-world application of data engineering using Microsoft Azure. The goal was to create a data pipeline that migrates data from an on-premises SQL Server database to the cloud. The pipeline is designed to run daily, triggered by the addition of new data to the database.
![overview](https://github.com/SardarBoy/AzureDataEngineering1/blob/80604db716f778381552bb1dd901dd997ac0e52f/Project%20Overview.png)

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



## Workflow
![resourcegroup](https://github.com/SardarBoy/AzureDataEngineering1/blob/73438a92dbf7c0bc03c336ffef31c0eae08119be/ResourceGroup.png)

1. **Data Ingestion**
   - Connect Azure Data Factory to the on-premises SQL Server database.
   - Copy the necessary tables to Azure Data Lake Storage Gen2.
![database](https://github.com/SardarBoy/AzureDataEngineering1/blob/982239a2a018033ea9ca9c0667c57018233eab40/Database.png)

2. **Data Transformation**
   - Use Azure Databricks to transform the ingested data into the required format. After ingesting data into the "bronze" folder, it undergoes transformation following the data lake architecture (bronze, silver, gold), becoming suitable for business reporting tools like Power BI. Azure Databricks, using PySpark, handles these transformations. Azure Data Factory is configured to automatically execute these transformations with each pipeline run.
![databricks](https://github.com/SardarBoy/AzureDataEngineering1/blob/c1e943c805dbfc465a49e29d6e7ec7ab67549220/Data%20mounting%20and%20Transforming.png)

3. **Data Loading**
   - Load the transformed data into Azure Synapse Analytics and Create a link from Azure Storage (Gold Folder) to Azure Synapse.
![pipeline](https://github.com/SardarBoy/AzureDataEngineering1/blob/73438a92dbf7c0bc03c336ffef31c0eae08119be/Pipeline.png)

4. **Data Visualization**
   - Use Power BI to create reports based on data from Azure Synapse Analytics.
![dashboard](https://github.com/SardarBoy/AzureDataEngineering1/blob/44233eb41ef8e66c9bde77e4d7a0ac6710719e83/Dashboard.png)



## Conclusion

This project demonstrates the ability to create an end-to-end ETL cloud solution using Azure.  
I tested this pipeline by adding 2 customers to the customerr table and triggering the pipeline to run. I also created a scheduled trigger. After the successful run of each trigger, I refreshed the Power BI report, which changed to reflect the new data from 847 customers to 849. This approach showed the data engineering pipeline worked as scheduled.

Limitation
   - The dataset used was small and did not require data cleaning (7mb total, 800 rows). This was done to keep compute + storage costs low for myself.

   - According to this project, I have showcased how I used Microsoft Azure to create an end-to-end data engineering pipeline. This pipeline used data from the on-premise SQL server database and loaded the data in Azure Data Lake Gen 2 storage. I performed the necessary transformations using Azure Databricks and loaded the data in Azure SQL Database. Using two levels of transformations, I ensured the data was ready for different use cases. Thus, I extracted the data using Power BI and created a report for presentation to relevant stakeholders. This report represents a practical use case of Azure in data engineering in gathering data and making it ready and reliable for use.




