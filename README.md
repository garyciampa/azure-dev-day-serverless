# Azure Dev Day - Serverless Exercise 

<!-- TOC -->
**Overview**: 

- [Requirements](#requirements)
- [Step 1: Setup Azure subscription and properties](#step-1-setup-azure-subscription-and-properties)
- [Step 2: Create an Azure Resource Group ](step-2-create-an-azure-rResource-rroup)
- [## Step 3: Create Cosmos DB resources](Step-3-Create-Cosmos-DB-resources)
- [Step 4: Create Function App](Step-4-Create-Function-App)
- [Step 5: Create Event Grid](Step-5-Create-Event-Grid)
- [Step 6: Test and view results](Step-6-Test-and-view-results)
- [Step 7: Clean up resources](Step-7-Clean-up-resources)


<!-- TOC -->


## Requirements

This example assumes the user already has an Azure subscription with contributor access. Additionally, Azure CLI has been installed, [How to install Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli).

## Step 1: Setup Azure subscription and properties

Initial login and subscription setup is a required prerequisite

````shell
export SUBSCRIPTION_ID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx

az login 
az account set --subscription $SUBSCRIPTION_ID
````
## Set variable properties for substitution 


````shell
export RESOURCE_GROUP=<business-unit-demo-azure-dev-day>
export REGION=<eastus2>
export COSMOSDB_ACCOUNT_NAME=cosmosdb-$RANDOM
export COSMOSDB_SQL_CONTAINER=sql-container-$RANDOM
export COSMOSDB_SQL_DATABASE=sql-database-$RANDOM
````

NOTE: The region location of the resource group may be different than the physical azure resources 

## Step 2: Create an Azure Resource Group 

[Create Azure Resource Group](https://docs.microsoft.com/en-us/cli/azure/group?view=azure-cli-latest#az_group_create) use the following command line:

````shell
az group create --name $RESOURCE_GROUP --location $REGION
````
  
## Step 3: Create Cosmos DB resources

Creating a Cosmos DB may be accomplished via the [Azure Portal](https://docs.microsoft.com/en-us/azure/cosmos-db/create-cosmosdb-resources-portal), or via the [Azure CLI](https://docs.microsoft.com/en-us/azure/cosmos-db/cli-samples).

### Create Cosmos DB service

To create the Azure Cosmos DB account use the following command lines:

````shell
az cosmosdb create --name $COSMOSDB_ACCOUNT_NAME --resource-group $RESOURCE_GROUP
````
 
## Step 4: Create Function App 

Placeholder for content and and [links](...)

- Azure Functions
<img src="media/Function-Apps.svg" width=100 height=100px>




````shell

````


## Step 5: Create Event Grid 
Placeholder for content and and [links](..)

````shell

````

## Step 6: Test and view results 
Placeholder for content and and [links](..)

````shell

````

## Step 7: Clean up resources 

Do NOT forget to remove the resources once you've completed the exercise, [Azure Group Delete](https://docs.microsoft.com/en-us/cli/azure/group?view=azure-cli-latest#az_group_delete)

```shell
 az group delete --name $RESOURCE_GROUP --yes
```
