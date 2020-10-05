# Operationalizing Machine Learning

Microsoft Azure, a cloud based solution, provides a machine learning solution which enables model training, deployment and consumption. The solution is used to work with the [Bank Marketing Dataset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv) by developing a production ready model, deploy and consume the model. In another stage, a pipeline was created, pulished and consumed. Find below the approach followed to complete the project.

- Step 1 - Authentication
- Step 2 - Auto ML Experiment
- Step 3 - Deploy the best model
- Step 4 - Enable Logging
- Step 5 - Swagger Documentation
- Step 6 - Consume Model Endpoints
- Step 7 - Create and Publish a pipeline
- Step 8 - Documentation

## Architectural Diagram

_TODO_: Provide an architectual diagram of the project and give an introduction of each step.

## Key Steps

### Step 1 - Authentication

In this step, following the `Az` command, Azure Machine Learning Extension was installed and enabled in the terminal. Next, the procedure was to create the service principal(SP) account - An identity that helps restrcitions based on roles assignment.
After creating the SP account, access was allowed to my workspace. Finally, ran the workspace share command successfully.

#### Service Principal

![Service Principal](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Service%20Principal.png)

#### Workspace Share

![Workspace Share](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/workspace%20share.png)

### Step 2 - AutoML Experiment

In this step, after the authentication step has been completed successfuly, the aim of this step is to provide a model for deployment and consumption. To do this, a new automl run was created, after the dataset was uploaded, and a new experiment was created. Configured a new compute cluster to run the classification machine learning experiment.

See image of the datasets, experiment, and model after the experiment below.

#### Datasets

![Datasets](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Dataset%20is%20available.png)

#### Completed Experiment

![Experiment](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Completed%20Experiment.png)

#### Best Model

![Best Model](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Best%20Model.png)

### Step 3 - Deploy the Best Model

After a succesful run of the experiment, the best model was selected, ddeployed using Azure Container Instance(ACI) with authentication enabled.

### Step 4 - Enable Logging

To retrieve logs after model deployment application insights has to enabled. The code file `logs.py` was well populated with details with application insights set to true and the code was executed.

#### Application Insights Enabled

![Insights](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Application%20insights%20enabled.png)

#### Logs Running

![Logs Running](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Logs%20running.png)

#### Logs Running Terminal

![Logs Running](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Logs%20running%20terminal.png)

### Step 5 - Swagger Documentation

In this step, after locating the Azure provided swagger json file, it was downloaded. A swagger container running on port 80, and the python file `serve.py` was used to create a serve that is listening on port 8000. Once the UI is created, the API is interacted with.
See below a screenshot of the Swaggger UI.

#### Swagger UI

![Swagger](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/New%20Swagger.png)
![Swagger 1](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/New%20Swagger%203.png)

### Step 6 - Consume Model Endpoints

At this point the model has been deployed, it's time to interact with the trained model. The `endpoint.py` is executed with the correct `scoring_uri` and `key` pouplated in the script.
A result is generated after running the script, and that is shown below.

#### Endpoint Result

![Endpoint](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Endpoint%20result.png)

### Step 7 - Create and Publish a Pipeline

In this step, the task is to create and publish a pipeline. The Jupyter Notebook is uploaded to the Azure ML studio. The right environment variables are provided, and the `config.json` is provided as well.
The code cells are executed and that creates the pipeline. See Below the screenshots from this step.

#### Create Pipeline

![Create Pipeline](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Created%20Pipeline.png)

#### Create Pipeline

![Create Pipeline](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Created%20Pipeline%202.png)

#### Pipeline Endpoint

![Pipeline Endpoint](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Pipeline%20Endpoint%202.png)

#### Pipeline Endpoint

![Pipeline Endpoint](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Pipeline%20Endpoint.png)

#### Banking Dataset with the AUTOML Module

![Banking](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Banking%20Dataset%20with%20the%20AutoML%20module.png)

![Banking](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Banking%20Dataset%20with%20the%20AutoML%20module%202.png)

#### Published Pipeline Overview

![Published Pipleine ](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Pipeline%20Endpoint%202.png)

#### Jupyter Notebook - UseRunWidget

![Run Widget](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Run%20Widget%20in%20Notebook.png)

#### Schedlued Run

![Scheduled Run](https://github.com/bleso-a/nd00333_AZMLND_C2/blob/master/Screenshot/Run%20in%20ML%20studio%202.png)

## Screen Recording

_TODO_ Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:
