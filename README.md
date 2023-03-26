# Overview

This project demonstrates the implementation of Continuous Integration and Continuous Delivery pipelines step by step by using a Python-based machine learning application and the Flask web framework in Github, Azure Portal and Azure DevOps platforms. 
After creating a Github Repository called AzureDevops, first Github Actions is used along with a Makefile, requirements.txt and application code to perform an initial lint, test, and install cycle to create Continuous Delivery. Then this project was integrated with Azure Pipelines to enable Continuous Delivery to Azure App Service.

## Project Plan
<TODO: Project Plan

* A link to a Trello board for the project
* A link to a spreadsheet that includes the original and final project plan>

## Instructions

<TODO:  
* Architectural Diagram (Shows how key parts of the system work)>

1. Create an Azure Account and install the Azure command line interface. 
2. Crate a GitHub repository called Flask_ML_app and clone this repository to the Azure CLI. 
3. In order to make connection between your Github account and Azure CLI, create ssh keys in Azure Cloud Shell and upload it to my GitHub account in the setting menu.
4. For continuous integration, after installing the required software’s and testing it by using Makefile, set up GitHub action as a build server—a centralized machine that is dedicated to continuously building the project every time when there is a change in the code. 
5. For continuous Delivery, first, set up Azure DevOps Pipeline Agent (a virtual machine) to perform the pipeline jobs, such as building the code residing in Github and deploying it to the Azure services. To do this;
  - Create a Personal Access Token (PAT), 
  - An Agent pool and a Linux VM and,
  - Configure the Linux VM as an Azure DevOps Build Agent and install Application-specific dependencies.
6. Set up a Service connection via Azure Resource Manager and Service principal to connect my DevOps account with my Azure account.
7. Create a Web App Manually and initially deploy the app in Cloud Shell. https://<Your_unique_app_name>.azurewebsites.net/.
8. As a final step deploy the application using Azure Pipelines into Azure App Services. For this, create a Pipeline and Edit the YAML file to build and deploy the app service successfully and test an application inside of Azure Pipelines

[Screenshot_action_passing.png](https://github.com/ebozcal/Flask_ML_Azure/blob/main/Screeshoots/Screenshot_action_passing.png?raw=true)

![image](https://user-images.githubusercontent.com/47538198/227804191-0181b58b-8d48-4f88-a4bd-96714b61a6c2.png)

* Project running on Azure App Service

* Project cloned into Azure Cloud Shell

* Passing tests that are displayed after running the `make all` command from the `Makefile`

* Output of a test run

* Successful deploy of the project in Azure Pipelines.  [Note the official documentation should be referred to and double checked as you setup CI/CD](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops).

* Running Azure App Service from Azure Pipelines automatic deployment

* Successful prediction from deployed flask app in Azure Cloud Shell.  [Use this file as a template for the deployed prediction](https://github.com/udacity/nd082-Azure-Cloud-DevOps-Starter-Code/blob/master/C2-AgileDevelopmentwithAzure/project/starter_files/flask-sklearn/make_predict_azure_app.sh).
The output should look similar to this:

```bash
udacity@Azure:~$ ./make_predict_azure_app.sh
Port: 443
{"prediction":[20.35373177134412]}
```

* Output of streamed log files from deployed application

> 

## Enhancements

<TODO: A short description of how to improve the project in the future>

## Demo 

<TODO: Add link Screencast on YouTube>


