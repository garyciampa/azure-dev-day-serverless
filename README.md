# Azure Dev Day - Serverless Exercise 

<!-- TOC -->
**Overview**: 

- [Requirements](#requirements)
- [Step 1: Setup Azure subscription and properties](#step-1-setup-azure-subscription-and-properties)
- [Step 2: Create an Azure Resource Group ](#step-2-create-an-azure-resource-group)
- [Step 3: Create Cosmos DB resources](#step-3-create-cosmos-db-resources)
- [Step 4: Create Function App](#step-4-create-function-app)
- [Step 5: Create Event Grid](#step-5-create-event-grid)
- [Step 6: Test and view results](#step-6-test-and-view-results)
- [Step 7: Clean up resources](#step-7-clean-up-resources)


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
export TAG_PREFIX=<business-unit>

export RESOURCE_GROUP=<$TAG_PREFIX-demo-azure-dev-day>
export REGION=<eastus2>

export COSMOSDB_ACCOUNT_NAME=cosmosdb-$RANDOM
export COSMOSDB_SQL_CONTAINER=sql-container-$RANDOM
export COSMOSDB_SQL_DATABASE=sql-database-$RANDOM

export STORAGE_ACCOUNT_NAME=stg${TAG_PREFIX}${RANDOM}
export FUNCTION_APPNAME=${TAG_PREFIX}-functionapp-${RANDOM}
````

NOTE: The region location of the resource group may be different than the physical azure resources 

## Step 2: Create an Azure Resource Group 

[Create Azure Resource Group](https://docs.microsoft.com/en-us/cli/azure/group?view=azure-cli-latest#az_group_create) use the following command line:

````shell
az group create --name $RESOURCE_GROUP --location $REGION --tags $TAG_PREFIX 
````
  
## Step 3: Create Cosmos DB resources

Creating a Cosmos DB may be accomplished via the [Azure Portal](https://docs.microsoft.com/en-us/azure/cosmos-db/create-cosmosdb-resources-portal), or via the [Azure CLI](https://docs.microsoft.com/en-us/azure/cosmos-db/cli-samples).

````shell
az cosmosdb create --name $COSMOSDB_ACCOUNT_NAME --resource-group $RESOURCE_GROUP --tags $TAG_PREFIX 
````
 
 
## Step 4: Create Function App  
<img src="media/Function-Apps.svg" width=75 height=75px>

This step combines elements of the Azure CLI and Azure portal to demonstrate the complimentary features. 

### Step 4A: Create Storage account and Function App service 
Creating a storage account and function app via the [Azure Portal](https://portal.azure.com), or via the [Azure CLI](https://docs.microsoft.com/en-us/azure/azure-functions/scripts/functions-cli-create-serverless).

````shell 
# Create storage account and function app service 
az storage account create --name $STORAGE_ACCOUNT_NAME --location $REGION --resource-group $RESOURCE_GROUP --sku Standard_LRS --tags $TAG_PREFIX 

az functionapp create --name $FUNCTION_APPNAME  --storage-account $STORAGE_ACCOUNT_NAME \
	--consumption-plan-location $REGION \
	--resource-group $RESOURCE_GROUP --functions-version 2 --tags $TAG_PREFIX
````

### Step 4B: Create HTTP Trigger 

Navigate to the Azure portal, and the resource group created previously. Select the <tag-prefix-functionapp-nnnn> "Function App", navigate the file tree and selct the 
<img src="media/functionselector.png" width=75 height=50> icon, and create a new "HTTP Trigger" Function, with a meaningful name, ie: "HelloHttpFunction". 

<img src="media/createfunctionapp.http.png" width=200 height=250px>

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
