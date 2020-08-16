# Azure Monitor - OpenCensus integration

This document captures the research that was completed to validate the process of setting up OpenCensus and sending monitoring data to Azure Monitor. The python file `azure_opencensus.py` serves as the proof of concept.

## Prerequisites

### Create an Azure Application Insights resource and get Instrumentation Key

To create an Application Insights resource in Azure and get the InstrumentationKey follow the guide: [Create an Application Insights resource](https://docs.microsoft.com/en-us/azure/azure-monitor/app/create-new-resource).

### Install Dependencies

The dependencies are also listed in the requirements.txt file.

```bash
pip install python-dotenv
pip install opencensus
pip install opencensus-ext-logging
pip install opencensus-ext-azure
```

## Run the project

In our sample we used Python 3.8.2, but the project should run on other 3.x versions as well.

1. Install the dependencies

```bash
pip install -r requirements.txt
```

2. Create a virtual environment

```bash
python -m venv .venv
```

2. Rename the `.env.sample` file to `.env`. This contains the environment variables that you need to set for your Azure Storage account. Set the `APPINSIGHTS_INSTRUMENTATIONKEY` variable in the .env file. 

5. Run the project!

```bash
python azure_opencensus.py
```

The created traces will be visible on your Application Insights instance:

![application_insights](./assets/application_insights.png)

## References

* [Microsoft docs: Azure Monitor for your Python application](https://docs.microsoft.com/en-us/azure/azure-monitor/app/opencensus-python)
* [Opencensus docs: Exporters -> Supported Exporters -> Python -> Azure Monitor](https://opencensus.io/exporters/supported-exporters/python/azuremonitor/)