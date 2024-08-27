# AOAI ChatGPT Demo using Streamlit

A fully python based Streamlit development harness for ChatGPT hosted in Azure OpenAI Service.

## Getting Started

### Setting up the Environment

To get started, you will need to create a `.env` file in the root of the project. This file will contain the environment variables needed to run the app. You can make a copy of `local.env` and rename it to `.env` to get started. You will need to fill in the following values:

AOAI_ENDPOINT
API_KEY
API_VERSION
subscription
resourcegroup
AOAI_AccountName

You can find the values for these variables in the Azure Portal. You will need to create an Azure OpenAI resource and deploy the ChatGPT model to it. Once you have done that, you can find the values for these variables in the resource.

The app will load this .env file using the python-dotenv library.

### Prerequisite: appsettings in Azure App Service

If you are deploying the app to Azure App Service, you will need to configure the app settings in the Azure Portal. Here is a list of the settings you need to add:

- `AOAI_ENDPOINT`
- `API_KEY`
- `API_VERSION`
- `subscription`
- `resourcegroup`
- `AOAI_AccountName`

### Running the App

To run the app, simply run the `streamlit run app.py`.  This will start the app on port 8501.  You can then access the app at `http://localhost:8501`. If running in a container, you will need to forward the port to your local machine if VSCode does not do it for you automatically.

### Devcontainer

This project is designed to be used with VSCode and the Remote Containers extension.  Once you have the extension installed, open the project in VSCode and you will be prompted to open the project in a container.  This will build the container and install all the dependencies.

### Python Dependencies

The `requirements.txt` file contains all the python dependencies for this project.  The `devcontainer.json` file will automatically install these dependencies when the container is built.


### Docker

```bash
$ docker login myregistry.azurecr.io

$ docker build --no-cache -t yourusername/app .

$ docker run -p 8501:8501 yourusername/app

$ docker tag yourusername/app myregistry.azurecr.io/app:v1

$ docker push myregistry.azurecr.io/app:v1
```