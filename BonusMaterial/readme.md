# Azure Function Apps on Kubernetes with Keda 

<!-- TOC -->
**Overview**: 

- [Objectives](#objectives)
- [Requirements](#requirements)
- [References](#references)

<!-- TOC -->

## Objectives 

This exercise combines elements Azure Functions, Azure Kubenetes (AKS), and, **enhances** AKS scaling using [KEDA](https://keda.sh/). Integrating and exploting KEDA adds another dimension to leveraging the array of Azure features to provide an organzation addtional flexibility and control for application deployment, scaling and management. Attractive features include:

- Event-drivin scaling
- Autoscaling simplified 
- Templates, built-in scalers based on workload type 
- Natural integration with Azure Functions and Kubernetes 

## Requirements 

- An Azure subscription (If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=azure-azuredevtips-azureappsdev)
- Latest version of [Visual Studio](https://code.visualstudio.com/?WT.mc_id=other-azuredevtips-azureappsdev)
- Alternatively, [Visual Studio Code](https://code.visualstudio.com/?WT.mc_id=other-azuredevtips-azureappsdev) with the [Azure Function extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions&WT.mc_id=other-azuredevtips-azureappsdev)
- Docker, on your PC to develop container-based applications. Download it [here](https://store.docker.com/editions/community/docker-ce-desktop-windows?WT.mc_id=other-azuredevtips-azureappsdev)
- The [Azure CLI](https://docs.microsoft.com/cli/azure/?WT.mc_id=docs-azuredevtips-azureappsdev). You can download it for [Windows, Linux or Mac](https://docs.microsoft.com/cli/azure/install-azure-cli?WT.mc_id=docs-azuredevtips-azureappsdev)
- Node.js, which includes npm that we need to install the [Azure Functions Core Tools](https://docs.microsoft.com/azure/azure-functions/functions-run-local?WT.mc_id=docs-azuredevtips-azureappsdev). Download [Node.js here](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm?WT.mc_id=other-azuredevtips-azureappsdev)
- [Azure Functions Core Tools](https://docs.microsoft.com/azure/azure-functions/functions-run-local?WT.mc_id=docs-azuredevtips-azureappsdev)


## References 

- [Part One: Azure Functions on Kubernetes with KEDA Part 1 of 2, Tip 277](https://microsoft.github.io/AzureTipsAndTricks/blog/tip277.html) 
- [Part Two: Azure Functions on Kubernetes with KEDA Part 2 of 2, Tip 278](https://microsoft.github.io/AzureTipsAndTricks/blog/tip278.html)


