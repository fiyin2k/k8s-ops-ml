[![fiyin2k](https://dl.circleci.com/status-badge/img/gh/fiyin2k/k8s-ops-ml/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/fiyin2k/k8s-ops-ml/tree/main)
## Project Overview

The Operationalize ML project contains a Machine Learning Microservice, built on a pre-trained, **sklearn** model that has been trained to predict housing prices. It contains a model that predicts house prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). 

## Project Tasks

- Run and start a docker container
- Test the prediction code using linting
- Deploy and make prediction using Docker container
- Upload the docker container into Docker Hub, a public Docker registry
- Configure a cluster within Kubernetes
- Run the deployed application in the Kubernetes cluster
- Integrate within CircleCI for continuous integration and indicate test status using CircleCI badge

## Requirements
**python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate**

## START HERE

### Step 0
- Fork this repo and clone it to your local workstation (obviously)

### Step 1: Install dependencies
- Set up  environment by running `make setup`. This will create a virtual environment in your home directory called `.devops`
- Install dependencies by running `make install`
- Lint application, requires hadolint

### Step 2: Run Docker container
- Run the application on docker by calling `./run_docker.sh`

### Step 3: Upload to Docker Hub
- In the `./upload_docker.sh` file, edit the dockerpath (line 8) and change the docker username to a personalized one (or leave it as is, to use the public kcemenike/microproject:v1.0.0)
- To upload to docker hub, run `./upload_docker.sh`

### Step 4: Kubernetes deployment
- To deploy to kubernetes, run `./run_kubernetes.sh`
