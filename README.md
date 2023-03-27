# Overview

This project demonstrates the implementation of Continuous Integration and Continuous Delivery pipelines step by step by using a Python-based machine learning application and the Flask web framework in Github, Azure Portal and Azure DevOps platforms. 
After creating a Github Repository called AzureDevops, first Github Actions is used along with a Makefile, requirements.txt and application code to perform an initial lint, test, and install cycle to create Continuous Delivery. Then this project was integrated with Azure Pipelines to enable Continuous Delivery to Azure App Service.

## Project Plan

* A link to a Trello board for the project:https://github.com/ebozcal/Flask_ML_Azure/blob/main/Screeshoots/trello.png?raw=true
* A link to a spreadsheet that includes the original and final project plan:https://github.com/ebozcal/Flask_ML_Azure/blob/main/Screeshoots/planning.png?raw=true

## Instructions

![image](https://user-images.githubusercontent.com/47538198/227804650-1b6e4532-d925-4608-867e-c83f2b620aa1.png)

1. Create an Azure Account and install the Azure command line interface. 
2. Crate a GitHub repository called Flask_ML_app and clone this repository to the Azure CLI. 
3. In order to make connection between your Github account and Azure CLI, create ssh keys in Azure Cloud Shell and upload it to my GitHub account in the setting menu : "ssh-keygen -t rsa"
5. For continuous integration, after installing the required software’s and testing it by using Makefile, set up GitHub action as a build server—a centralized machine that is dedicated to continuously building the project every time when there is a change in the code. 
6. For continuous Delivery, first, set up Azure DevOps Pipeline Agent (a virtual machine) to perform the pipeline jobs, such as building the code residing in Github and deploying it to the Azure services. To do this;
  - Create a Personal Access Token (PAT), 
  - An Agent pool and a Linux VM and,
  - Configure the Linux VM as an Azure DevOps Build Agent and install Application-specific dependencies.
7. Set up a Service connection via Azure Resource Manager and Service principal to connect my DevOps account with my Azure account.
8. Create a Web App Manually and initially deploy the app in Cloud Shell. https://<Your_unique_app_name>.azurewebsites.net/.
9. As a final step deploy the application using Azure Pipelines into Azure App Services. For this, create a Pipeline and Edit the YAML file to build and deploy the app service successfully and test an application inside of Azure Pipelines


* Project running on Azure App Service
After creating your webapp, deploy it to Azure app services by using Azure CLI:
az webapp up -n <your_webapp_name> --sku F1 --resource-group <your_resource_group>
When you go to the"https://<Your_unique_app_name>.azurewebsites.net/" you can see:
![image](https://user-images.githubusercontent.com/47538198/227805165-301e4bbd-761f-434d-8257-3746496218d6.png)
* Project cloned into Azure Cloud Shell
![image](https://user-images.githubusercontent.com/47538198/227804273-c1d72551-62fd-44c3-8dc4-d785accda905.png)

* Passing tests that are displayed after running the `make all` command from the `Makefile`
![image](https://user-images.githubusercontent.com/47538198/227804388-6644b88b-04b1-4732-80e8-2c6dfb302465.png)

* Output of a test run
![image](https://user-images.githubusercontent.com/47538198/227804191-0181b58b-8d48-4f88-a4bd-96714b61a6c2.png)
![image](https://user-images.githubusercontent.com/47538198/227804523-d76521a5-5fd3-4d5b-9417-64f17abca0b3.png)
* Successful deploy of the project in Azure Pipelines.  [Note the official documentation should be referred to and double checked as you setup CI/CD](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops).
![image](https://user-images.githubusercontent.com/47538198/227804570-49ace199-87b9-49ea-9d70-60c056e97a5e.png)
* Running Azure App Service from Azure Pipelines automatic deployment
![image](https://user-images.githubusercontent.com/47538198/227805577-63c3c63d-8f50-4c13-8d41-76f16083438b.png)
* Successful prediction from deployed flask app in Azure Cloud Shell.  [Use this file as a template for the deployed prediction](https://github.com/udacity/nd082-Azure-Cloud-DevOps-Starter-Code/blob/master/C2-AgileDevelopmentwithAzure/project/starter_files/flask-sklearn/make_predict_azure_app.sh).
![image](https://user-images.githubusercontent.com/47538198/227804717-553171e9-23e4-4860-8288-2b1c1a16f5db.png)
The output should look similar to this:

```bash
udacity@Azure:~$ ./make_predict_azure_app.sh
Port: 443
{"prediction":[20.35373177134412]}
```

* Output of streamed log files from deployed application
![image](https://user-images.githubusercontent.com/47538198/227804769-f8ea31ad-80fe-41c0-adc8-c1287be5dece.png)
* Demonstration of Continuous Delivery process on the Azure platform.
Changing the application name in app.py from 'Sklearn Prediction Home' to 'Sklearn Prediction Continious integration' and commit it:
![image](https://user-images.githubusercontent.com/47538198/227893674-b2989c40-3209-4899-8b4a-9d993ea2fab1.png)

## Enhancements
You can extend this project by using different app rather than ML app and you can try different platforms todo this kind of CI/CD project rather than GitHub and azure paltforms

## Demo 

https://youtu.be/9WKCpIS6BhE


