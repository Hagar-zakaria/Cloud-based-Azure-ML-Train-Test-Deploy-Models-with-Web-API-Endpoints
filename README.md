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

# Launching the machine learning studio

1. After creating the workspace, it’s time to launch the ML studio, and it will look like the image below.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/6289af57-430e-4c49-9d25-a4236dfd0f9c)

2. Make a new storage account to avoid the files of other storage systems.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/937e64db-acfe-4d34-893c-4ef14e0d60da)

3. Now, create a container inside this storage account.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/da5e808d-0ccf-4f48-af65-192e3a59aa4a)

4.Now, create a data store in the ML studio that will connect to this newly made storage account.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/7b642b2e-c301-4743-a05a-44fbf87862fa)

5. Fill in the information.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/0acda462-ccc2-428a-983e-5438ab42cecd)

To get the access key, go to the new storage account in step 2 and copy the key from the access key option, as shown below.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/82b1a8b2-9139-414e-92bf-1a22228cdaec)

6. Now, upload the dataset to the container we created in the storage account in step 3.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/5ffd51ef-58ca-431b-a9ec-7701565628ae)

We also check the file through the storage browser option in the storage account.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/e56a2722-ad7f-4e2f-bdfb-05f31da6a50f)

7. Now, create the dataset and choose the file from the data stores.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/3983da22-39db-49a4-94dc-d5c45ea5909e)

Click the next button; when we will select ‘From Azure storage’ other options will come on the left side. We choose this option because our storage is a blob type.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/8def5bfc-4b87-4882-affd-69675f85e3a3)

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/b7b9cbd6-26dc-44e1-99fd-f063cc2a0410)

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/a75759c4-5bce-49e9-98fc-ae95f517a988)

Now, we can deselect the Loan_ID and Gender column in the Schema option.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/5bdae3d7-ec31-4b82-bdd9-162e6f799b9b)

Our data is uploaded in the dataset.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/b2497931-fd28-4f8b-815b-1fdc01dde10f)
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/c2a12550-c5d1-48bb-9b9b-28de31f0d09e)

# Compute Resources

In this topic, we will discuss the managed resources artifacts i.e. compute instances and compute clusters that come in the machine learning workspace.

These are just different names for computers and virtual machines. The computed target is connected with linked services in the workspace.

# Why do we need computing resources?

For any machine learning modeling, we need a computation resource that will train our model.

1. Compute instance: It is a type of virtual machine/server or computer that is used for cloud computation. It is not a machine only but connected to the workspace and has Python, R, Docker, and Azure ML SDK configured. The default storage account while creating the workspace is attached to this instance means we can access all notebooks and other data stored. Mostly used in a development process training, testing, and inferencing. Inference means creating endpoints for web services.

2. Compute clusters: It is also a managed resource that is a group of virtual machines. We can use the clusters for all three authors i.e.compute instance, designer, or autoML, for training and with limited deployment.
   
3. Compute targets: These compute consist of remote/attached compute and Inference clusters.

**Remote compute**: The primary aim of the target is used for training and testing the deployment. We can use any local machines, compute instances or virtual machines as a compute target. We can also use batch inferencing on compute clusters.

**Inference clusters**: It is used to do real-time predictions in production using our model. They can be Azure Kubernetes Service (AKS).

# Creating the compute clusters

1. Go to the compute tab and find the compute cluster option in ML studio as shown below:
   ![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/d61b2fcd-20fa-48b3-86ca-32bf80bdfd42)

2. Now, choose the compute with a low budget as we are just practicing.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/8f3af097-fc8e-4927-aac1-0bf38ede0e63)

3. Give the name of the cluster and click on the create button.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/0982ecfd-dc03-43eb-a54e-6f91a1e234f8)

4. Also, create a compute instance as shown below with the same information as above.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/05081573-9295-4457-819c-ba49b7b84f58)

# What is a pipeline?

It is just a series of tests or workflow from data processing to deployment.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/8dab94da-1724-45a8-b332-0d8f3564f988)

We may need to create compute instances at the time of cleaning and training processes.

# Creating a new training pipeline using a designer from the ML studio dashboard

1.Click on the start now button in the designer option as shown below:

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/b3b8cde1-bbdd-4b52-b0aa-536df5b9e337)

2. Now click on the plus button to create the pipeline.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/99000080-4738-4ca1-8cad-ca6a3d588604)

3. The pipeline interface will open after clicking on the plus button.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/289d0b08-5ace-4edd-8d07-d25ecb5efb6d)

4. In our data option we have our dataset as shown in the below image:

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/cc5d9437-2a55-4134-9d7f-3ae40218ad34)

5. Just drag and drop the data to the right side.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/6d5e6fef-2329-4684-89a4-96a85be82ac7)

6. Now, check for the selected columns from the dataset in the component option and drop them on the right side. Connect the output of the dataset to the input of the select column.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/3596cc80-e55b-4146-a5cf-aed552d2689b)

7. Now, double-click on the select column then click on the edit columns.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/f082e824-8d66-49b9-a079-9f144f53e59e)

8. Now choose the clean missing option and choose the column in the edit column button.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/d08a9402-5370-47b0-ad63-b0a4094d14a7)

9. Now choose the split option and then select the fraction as ‘0.7’ and also select the stratified column with column name ‘loan_status’ through the edit column.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/f5b52360-75f9-478c-877a-dd6e8ae74ff6)

10. Now, we are ready to train our two-class logistic regression model.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/5192a847-239c-4357-ab54-dc2909c694b1)

11. After all the options in the canvas, our pipeline is complete. Now go to settings to choose compute clusters.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/384e4926-adda-48f2-ae4f-658634fdf347)

12. Suppose our training model is big and we need to use a different compute cluster. Then we can choose the train model option and choose another compute in Run Settings as shown below:

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/40ceb4fd-78f4-4eb6-9132-bc304df21df6)

13. Our pipeline is complete, we can click on the submit button to run the pipeline.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/458048d6-db2d-4245-a78c-5448c4606d0d)

Our pipeline running is completed successfully.

14. After completing, right-click on the Evaluate model to see the ROC curves.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/7b27b8a9-c95d-471b-a86d-626507cd1ca8)

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/39c9387d-5ddd-4773-9a85-5066870d2348)

# Creating Inference Pipeline and deploying it as a web service

1.After completing the pipeline, we can get the create inference pipeline option as shown below:
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/adabb5e4-d031-4fd1-ad89-3827ad5c5fac)

2. When we choose real-time inference, azure do some changes in the pipeline as shown below:
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/afc165a0-689e-413c-a1a8-4eb71a74cd20)

3. We did some changes in the pipeline as shown below:
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/4627a968-5049-4da1-8929-92e5336085b6)

4. Now click on the submit button to run the real-time inference. After completing the automation, we can check the scores.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/6740fb8e-4944-4630-a2c7-11cc45cb869a)

We got the scores and probabilities also.

5. But we need only score labels in the web service output, so we will need a select column option in the canvas to limit the output.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/2d5ef645-83e7-459d-b832-361bfca4d6a8)

6. To make the predictions, we need to deploy the model in the cloud, if the deploy button is shown, then refresh the page after submitting run completion.

But before deployment, we need an Azure Kubernetes Cluster service for that need to make a new inference cluster from the ML studio.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/b0ff08ac-3eae-4341-a7ec-79d83576ab49)

Choose the virtual machine configuration.
![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/0d2138d4-e16e-4942-ab96-86a4fdef955e)

Write the name of the cluster for the endpoint.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/8e668bc8-ddd8-46ce-a90d-3feb8b891582)

Now click on the create button to make the cluster, after some minutes it is completed successfully.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/1f4b360a-d617-4751-bab9-60a2f8d41aa2)

After the creation of an inference cluster, now it’s time to deploy the model and make the endpoints.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/87fd3687-84f8-4b5a-bf03-6ca54f6d9a3e)

Give the name of the endpoint and select the newly made inference cluster and click on the deploy button as shown below:

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/8a312417-b887-4296-b997-0ab5e9c8e6af)

After a few minutes, the deployment is complete and in the endpoint section we will see the endpoint in a healthy state.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/e55c44e7-e520-4713-98b4-28de346f5a85)

In the test section, we can make the prediction based on the input parameters.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/2cf5a96b-db9e-4995-8668-837366909dc5)

In the consume section, we can use the URL for scores.

![image](https://github.com/Hagar-zakaria/Cloud-based-Azure-ML-Train-Test-Deploy-Models-with-Web-API-Endpoints/assets/93611934/f925604b-98b4-46ab-91cc-37dd5a89fbd2)
