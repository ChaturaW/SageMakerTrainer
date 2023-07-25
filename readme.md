#Installation & configuration

- Create a domain
- Create a user profile in SageMaker studio under the domain
- Create a custom notebook kernel. This is for creating a python 3.9 kernel:
  - conda create --name <ENVIRONMENT_NAME> python=3.9
  - conda activate <ENVIRONMENT_NAME>
  - conda install ipykernel
- Create a new notebook by selecting the new environment or change the opened notebook’s kernel from UI - e.g. select "Python [conda env:custom_py39_1]"


# Model deployment
- Deploy the model for embedding
- Deploy the LLM
- Test the deployment of the models
  - If deployed via Jumpstart - Test the deployment by running the example notebook given by Jumpstart 
  - Will have to install the dependencies such:
    - langchain
    - sagemaker
    - bs4
    - faiss-cpu


# Running the steamlit app inside SageMaker studio
- Open the System Terminal from AWS SageMaker studio
- move inside the powersensor-chatbot folder
- install streamlit (pip install streamlit)
- similarly install sagemaker, boto3, json
- run the following command: $ streamlit run app.py 
- run with the following argument if want to apply changes on the fly:  $ streamlit run app.py --server.runOnSave true
- Open the URL: https://<sagemaker_domain_id>.studio.ap-southeast-2.sagemaker.aws/jupyter/default/proxy/8501/ e.g. https://d-rqgx355zgpuj.studio.ap-southeast-2.sagemaker.aws/jupyter/default/proxy/8501/
