# nlp-model-deploy1
Design an end-to-end nlp project with code upto full deployment on Cloud.
All the configs should be stored in yaml files, which will be read and updated by code.
Whenever new changes are pushed to repo, it will trigger a CI-CD pipeline.

Goal of the Project would be to verify the old saying 
<h3> Buy the rumour and sell the news </h3>

# Stages
## Stage 1
  - Design a Data Ingestion Pipeline which basically crawls web or might use old news data sources
  - Testing: Enforcing of Data Schema
  - Dockerfile, Testing, Endpoint

## Stage 2
  - Data Cleaning Pipeline
  - Saving data to local/remote database
  - Dockerfile, Testing

## Stage 3
  - Basic Data Cleaning and Preprocessing
  - Application of AutoML libraries
  - Dockerfile, Testing

## Stage 4
  - Model Experiments
      - Based on different models, conduct experiments with different hyperparameters
      - Use MLFlow with remote tracking and artifact server to run experiments
      - Dockerfile, Endpoint, Testing
   
## Stage 5
  - From MLFlow Tracking Server, compare models and push final model to Model Registry
        - Staging
        -  Production
    The information is then added to config files, which are then pushed to repo and then CI-CD pipeline triggers deployment
  - Dockerfile, Endpoint, Testing

## Stage 7
  - Create Endpoints
  - Dockerfile, Endpoint, Testing

## Stage 6
  - Create CI/CD Pipeline to
      - Read data from config file for current best model
      - Load model files from remote server into local image
      - Build and Push images to Container Registry
      - Deploy the containers via endpoint(s) using Kubernetes
