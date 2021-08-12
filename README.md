# Azure Dev Day - Serverless Exercise 

## Prerequisites 

## Set Azure subscription and properties subscription

````shell
  export RESOURCE_GROUP=demo-azure-dev-day
  export REGION=eastus2
  export COSMOSDB_ACCOUNT_NAME=cosmosdb-$RANDOM
  export COSMOSDB_SQL_CONTAINER=sql-container-$RANDOM
  export COSMOSDB_SQL_DATABASE=sql-database-$RANDOM
````

NOTE: The region location of the resource group may be different than the physical azure resources 

## Create an Azure Resource Group 

To create the Resource Group use the following command line:

````shell
  az group create --name $RESOURCE_GROUP --location $REGION
````
  
## Create Cosmos DB resources, to include Cosmos DB, Database and Container 

### Create Cosmos DB service

To create the Azure Cosmos DB account use the following command lines:

````shell
  az cosmosdb create \
    --name $COSMOSDB_ACCOUNT_NAME \
    --resource-group $RESOURCE_GROUP
````

### Create Cosmos DB Database 

To create the SQL database use the following command lines:

````shell
  az cosmosdb sql database create \
    --resource-group $RESOURCE_GROUP \
    --account-name $COSMOSDB_ACCOUNT_NAME \
    --name $COSMOSDB_SQL_DATABASE
````


### Create Cosmos DB Container 

````shell
 

  az cosmosdb sql container create \
    --resource-group $RESOURCE_GROUP \
    --account-name $COSMOSDB_ACCOUNT_NAME \
    --database-name $COSMOSDB_SQL_DATABASE \
    --name $COSMOSDB_SQL_CONTAINER \
    --partition-key-path '/id'
````
 
## Create Function App 


## Create Event Grid 


## Clean up resources 

Do NOT forget to remove the resources once you are done running the example.

```shell
 az group delete --name $RESOURCE_GROUP --yes
```
