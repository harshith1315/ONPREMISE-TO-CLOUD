# ONPREMISE TO CLOUD

![image](https://github.com/harshith1315/ONPREMISETOCLOUD/assets/111886682/7f5b7c0c-7375-457c-8dd3-012775809ad6)


On-premise to cloud architecture enables organizations to transition their IT infrastructure and applications from on-premise environments to the cloud. This shift offers scalability, flexibility, and cost-efficiency advantages, allowing businesses to streamline operations, drive innovation, and focus on core competencies. By migrating to the cloud, organizations can reduce hardware investments, optimize resource allocation, and leverage cloud-native services for enhanced performance and growth. Careful planning, security considerations, and skilled resource management are crucial for a successful migration. Overall, on-premise to cloud architecture empowers businesses to adapt, scale, and thrive in the dynamic digital landscape.


There a certain steps to migrate the data from on-premise to cloud.The above architecture give a clean and good picture about the data migration.We are migrating the data by using AZURE DATAFACTORY in #AZURE CLOUD.Follow the below steps for data migration.

# 1.ACCESS DATA
Connect to your local database:
Use the appropriate database client or command-line tool to connect to your local database.
Ensure you have the necessary credentials and connection details to establish a connection.
Select the database:

Once connected, use the SQL command "USE <database_name>" to select the specific database where your data is stored.
In your case, you mentioned the database name as "harshith". So, the command will be: "USE harshith";

Retrieve data from the table:

To view the data in the "customers" table, use the SQL query "SELECT * FROM customers".
Execute this query, and it will fetch all the records from the "customers" table in your selected database.

# 2.SETTING UP MICROSOFT INTEGRATION RUNTIME

Download Microsoft Integration Runtime:

Visit the download link provided: https://www.microsoft.com/en-us/download/confirmation.aspx?id=39717
Download the Integration Runtime installer suitable for your operating system.

Create an Integration Runtime instance in Azure Data Factory:

Sign in to the Azure portal (portal.azure.com).
Create or navigate to your Azure Data Factory instance.
Go to the "Integration Runtimes" section within the Data Factory.
Create a new Integration Runtime instance and configure it with the appropriate settings, such as name, region, and connectivity options.
Once created, note down the keys for the Integration Runtime instance.

Install and configure the Microsoft Integration Runtime:

Run the downloaded Integration Runtime installer on your local machine.
Follow the installation instructions and provide the necessary details when prompted.
During the installation, you will be asked to enter the Integration Runtime instance keys obtained from Azure Data Factory.
Provide the keys to establish the connection between the Integration Runtime on your machine and the Azure Data Factory instance.

Create a new dataset:

In the Azure Data Factory portal, go to the "Author & Monitor" section.
Click on the "Author" button to enter the Data Factory authoring experience.
Navigate to the "Author" tab if not already selected.

Define the dataset properties:

Click on the "New Dataset" button to create a new dataset.
Select the appropriate data store type based on your integration runtime. For example, if you are connecting to an on-premises SQL Server, choose the "SQL Server" data store type.
Provide a name for the dataset and specify any relevant properties or settings required to connect to your data source.
For example, if connecting to a SQL Server, you would specify the server name, database name, authentication method, credentials, and other connection details.

# 3 CONFIGURING AZURE SQL DATABASE

Create a Cloud SQL Database:

Sign in to the Azure portal (portal.azure.com).
Navigate to the Azure SQL Databases section.
Click on "Create" to create a new Azure SQL Database.
Follow the prompts to specify the database name, resource group, server, pricing tier, and other settings.
Review and create the database.

Create a Linked Service:

In the Azure Data Factory portal, go to the "Author & Monitor" section.
Click on the "Author" button to enter the Data Factory authoring experience.
Navigate to the "Manage" tab if not already selected.
Click on the "New Linked Service" button.
Select the appropriate connector for your Cloud SQL database (e.g., Azure SQL Database).
Provide a name for the Linked Service and configure the necessary settings, such as server name, database name, authentication method, and credentials.
Test the connection to ensure it's successful.
Save and publish the Linked Service.

Create a Dataset:

In the Azure Data Factory authoring experience, navigate to the "Author" tab.
Click on the "New Dataset" button.
Select the appropriate dataset type for your Cloud SQL database (e.g., Azure SQL Table or Azure SQL Query).
Provide a name for the Dataset and configure the necessary settings, such as the Linked Service (select the previously created Linked Service), table name, query, or other relevant details.
Define any additional properties, such as schema mapping or column mapping, if required.
Save and publish the Dataset.

# 4.CREATING A PIPELINE FOR COPY ACTIVITY

Open Azure Data Factory:

Sign in to the Azure portal (portal.azure.com).
Navigate to your Azure Data Factory instance.

Create a new pipeline:

In the Azure Data Factory portal, go to the "Author & Monitor" section.
Click on the "Author" button to enter the Data Factory authoring experience.
Navigate to the "Author" tab if not already selected.

Define the pipeline properties:

Click on the "New pipeline" button to create a new pipeline.
Provide a name for the pipeline and any relevant description or metadata.

Add Copy activity:

Within the pipeline, click on the "Add" button and select "Copy data" from the menu.
Configure the source and destination datasets for the Copy activity.
Select the appropriate datasets that represent the source and destination data sources, ensuring they are compatible with the Integration Runtime.

Configure the Copy activity:

Customize the settings and options for the Copy activity based on your data transfer requirements.
Specify the mapping of columns or data transformations if needed.
Define any filters or conditions to limit the data being copied.

Validate and test the pipeline:

Validate the pipeline configuration to check for any errors or warnings.
Test the pipeline by executing a debug run to verify the data transfer between the source and destination.
Monitor the execution and review the results for any issues or errors.

Publish the pipeline:

Once the pipeline is configured and tested successfully, click on the "Publish All" button to save and publish the changes to your Data Factory.

# 5.SUMMARY


Assess and plan your migration strategy and select the appropriate cloud services.
Set up the cloud environment and configure networking and security.
Install and configure the Integration Runtime tool for data movement.
Extract and transform data from on-premises sources.
Create datasets and linked services in Azure Data Factory.
Develop pipelines for data ingestion, transformation, and loading into the cloud.
Monitor and validate the data migration process.
Update applications/systems to use the new cloud data sources.
Optimize and fine-tune the cloud environment for performance and cost-efficiency.
Ensure that the data copy is present in the Azure Sql Database.
Ensure data security and compliance measures are in place.
Decommission or repurpose the on-premises data sources once migration is complete.

