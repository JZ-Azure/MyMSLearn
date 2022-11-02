## Azure Machine Learning studio
Machine Learning compute
- Compute instance
- Compute cluster
- Inference cluster
- Attached compute

## Azure Automated Machine Learning
An automated machine learning capability that **_automatically tries multiple pre-processing techniques and model-training algorithms in parallel_**.

### Prepare data
In Azure Machine Learning, data for model training and other operations is usually encapsulated in an object called a _dataset_.
### Train model

Only support **_supervised_** machine learning models.
- Classfication
- Regression
- Time series forecasting

### Deploy a predictive service
- n Azure Machine Learning, you can deploy a service as an Azure Container Instances (ACI) or to an Azure Kubernetes Service (AKS) cluster. 
- For production scenarios, an _AKS deployment is recommended_, for which you must create an inference cluster compute target.

## Exercise
[Explore Automated Machine Learning in Azure ML](https://learn.microsoft.com/en-us/training/modules/use-automated-machine-learning/6-exercise)
