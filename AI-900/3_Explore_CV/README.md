## Introduction
- Microsoft's Computer Vision service gives you access to _pre-trained_ computer vision capabilities.

## Azure resources for Computer Vision
- **Computer Vision**: A specific resource for the Computer Vision service. Use this resource type if you don't intend to use any other cognitive services, or if you want to track utilization and costs for your Computer Vision resource separately.
- **Cognitive Services**: A general cognitive services resource that includes Computer Vision along with many other cognitive services; such as Text Analytics, Translator Text, and others. Use this resource type if you plan to use multiple cognitive services and want to simplify administration and development.
- **Custom Vision**: Common techniques used to train image classification models have been encapsulated into the Custom Vision cognitive service in Microsoft Azure. You can use the Custom Vision cognitive service to train image classification models and deploy them as services for applications to use.
  - Can be either a training, a prediction or a both resource.
    - Creating a Custom Vision resource for both training and prediction results in **two separate resources** being provisioned, each with their own key and endpoint.
    - A **single cognitive service resource** can be used for both training and prediction.
  - Enables you to create object detection models

### Image analysis types
- Image description
- Tagging visual features
- Detecting objects
- Detecting brands
- Detecting faces
- Categorizing an image
- Detecting domain-specific content
- Optical character recognition

### Object detection
An object detection model returns the following information:
- The **class** of each object identified in the image.
- The **probability score** of the object classification.
- The **coordinates of a bounding box** for each object.

## Model training and evaluation
- **Precision**: What percentage of class predictions did the model correctly identify? For example, if the model predicted that 10 images are oranges, of which eight were actually oranges, then the precision is 0.8 (80%).
- **Recall**: What percentage of the class predictions made by the model were correct? For example, if there are 10 images of apples, and the model found 7 of them, then the recall is 0.7 (70%).
- **Mean Average Precision** (mAP): An overall metric that takes into account both precision and recall across all classes.










