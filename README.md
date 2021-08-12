# Azure Dev Day - Serverless Exercise 

## Prerequisites 

## Set Azure subscription and properties subscription

To setup the environment, recommendation is to set properties for variable substituion, simplifies changes and facilitates automation. Update properties as desired.

```shell
  export RESOURCE_GROUP=demo-azure-dev-day
  export REGION=eastus2
```

NOTE: The region location of the resource group may be different than the physical azure resources 

## Create an Azure Resource Group 

To create the Resource Group use the following command line:

```shell
  az group create --name $RESOURCE_GROUP --location $REGION
'''
  
## Create Cosmos DB 


## Create Function App 


## Create Event Grid 


## Clean up resources 

Do NOT forget to remove the resources once you are done running the example.

```shell
 az group delete --name $RESOURCE_GROUP --yes
```

