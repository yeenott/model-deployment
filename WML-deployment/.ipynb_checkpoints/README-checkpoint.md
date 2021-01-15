# A Tutorial of Model Depolyment on IBM Waston Machine Learning (WML)

## Steps to carry out before running the tutorial notebook

1. Logon in IBM Cloud, and Create a WML service
2. Create a deployment space by specifying a cloud storage object and the Watson Machine Learning instance
3. Find and copy the Space ID
4. [Generate an API key](https://cloud.ibm.com/iam/apikeys) and copy the generated API key.
5. Write the following lines with the relevant replacements and save this file as wml.json inside ""~/.ibm" or specified directory. 
  {
  "apikey": "YOUR API KEY",
  "url": "https://us-south.ml.cloud.ibm.com"
   }

## Create a virtual environment for WML
1. Create the Python environment. The Watson Machine Learning (WML) service has very specific [runtime requirements](https://dataplatform.cloud.ibm.com/docs/content/wsj/analyze-data/pm_service_supported_frameworks.html). So developing and training a model locally and then deploying it means that you will need to ensure a specific version of Python and specific package versions.

```bash
~$ conda create -n py3.7 python=3.7 anaconda
```

2. Ativate the environment and install the specific version of the packages available in the following requirements file. 

```bash
~$ conda activate py3.7
~$ pip install -r requirements.txt
```

## Deploying the model

1. Download the following scripts and the data to a location on your machine.
2. Activate the virtual environment (py3.7)

```bash
~$ conda activate py3.7
```

3. Open the "WML-tutorial-deploy-model.py" and edit the path to the data file and Json file, input the Deployment Space ID

```bash
~$ python WML-tutorial-deploy-model.py
```

4. Once the script has run, two tokens are printed : The "model_uid" the "deployment_uid". Copy those values in the "WML-tutorial-test-model.py". 

```bash
~$ python WML-tutorial-test-model.py
```