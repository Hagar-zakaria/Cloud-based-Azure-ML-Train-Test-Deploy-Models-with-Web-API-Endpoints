# Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/1a37d2f7-fedc-420d-a4fa-9de06a8fb8a0)

# Dependencies
- Azure Storage account: Used for the administration and the working of the workspace.
- Azure container registry: When we deploy our model to the production and docker instances.
- Azure key vault: To store various keys, secret information, and privacy information.
- Azure application insight: It is used to monitor our machine learning applications and various information like response time, requests, failure conditions, performance, etc.

# Basic concepts
**Datasets**
It is information composed in the form of rows and columns, i.e., a collection of data. There are many methods in azure to upload/fetch the dataset for machine learning experiments.

**Data-stores**
When we want to fetch the dataset from the local system, then we need some storage that is where the data store comes into the picture. Data-store is just the connection to the various storage types like account storage, database, or analytics as a data lake.

**Various storage types**
Blob, file storage, data lake, Azure SQL, Azure PostgreSQL, MySQL, Azure Data bricks. These are supported by the azure system.

# Creating the machine learning workspace

Below are the following steps to create the workspace

1. Open the azure dashboard, search for the machine learning resource, click on it and then create. If you don’t have an azure account, then follow the link below.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/c4bbba7c-f821-4efb-918d-fbcea04c7903)

2. Fill in all the information.
   ![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/b82624aa-ddeb-48ec-8b14-4d79b0ed5789)

If there is no resource group name, then create a new one. When we will write the workspace name, the other information like a key vault, storage account, and application insight is filled automatically. We will keep the container registry to ‘None’ for now because it is required at the time of deployment.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/a6666a0a-2301-4175-9770-f8eace293015)


3. After getting the Validation passed, click on create to make the workspace. It will create the four resources as shown below.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/bd73b452-8216-40b2-871e-ad7f61ec84c2)

4. Now, click on the go to the resource, and the workspace dashboard will open with the launch studio option as shown below.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/15e8c943-3546-41dd-8d50-46371a51beb9)

