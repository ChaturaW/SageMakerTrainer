# Installation & configuration

- Create a domain in AWS SageMaker
- Create a user profile in SageMaker studio under the domain
- Create a custom notebook kernel. This is for creating a python 3.9 kernel (This step is important as some models will not work in the default python version comes with the notebook):
  ```
  - conda create --name <ENVIRONMENT_NAME> python=3.9
  - conda activate <ENVIRONMENT_NAME>
  - conda install ipykernel
  ```
- Create a new notebook by selecting the new environment or change the opened notebook’s kernel from UI - e.g. select "Python [conda env:custom_py39_1]"


# Model deployment

- The models for **embedding** and for answer generation (**LLM**) has to be deployed
- The models can be deployed either from Jumpstart or using code (studio notebook/script).

  ## Deploy from Jumpstart:
  - Open Amazon SageMaker Studio
  - Open **SageMaker Jumpstart > Models, notebooks, solutions** from the left menu
  - Select the model for deployment
  - Update deployment configuration
    e.g: Select the **SageMaker hosting instance**, **Endpoint name**
  - Press **Deploy**
    
    ![image](https://github.com/ChaturaW/SageMakerTrainer/assets/35030369/af042c66-2c13-4044-891a-667d99d214d1)

  
  Deploy a model using a notebook:
  - Open the notebook https://github.com/ChaturaW/SageMakerTrainer/blob/main/Notebooks/text2text-flan-t5-large.ipynb
  - Change the necessary variables to select the model for deployment
  - Select the python 3.9 custom kernel as the notebook kernel
  - Run the notebook
  
  Test the deployment of the models
  - If deployed via Jumpstart - Test the deployment by running the example notebook given by Jumpstart    
  - Irrespective of the deployment method the dependencies for the code will need to be installed:
    


# Running the steamlit app inside SageMaker studio
- Open the System Terminal from AWS SageMaker studio
- move inside the app folder
- install streamlit (`pip install streamlit`)
- similarly install `sagemaker`, `boto3`, `json`
- run the following command: `$ streamlit run app.py` 
- run with the following argument if want to apply changes on the fly:  `$ streamlit run app.py --server.runOnSave true`
- Open the URL:
  - `https://<sagemaker_domain_id>.studio.ap-southeast-2.sagemaker.aws/jupyter/default/proxy/8501/`
  - e.g. `https://d-rqgx355zgpuj.studio.ap-southeast-2.sagemaker.aws/jupyter/default/proxy/8501/`
