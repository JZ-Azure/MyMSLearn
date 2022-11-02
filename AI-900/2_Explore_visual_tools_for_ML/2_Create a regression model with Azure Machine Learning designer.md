## Azure Machine Learning designer
- In Azure Machine Learning studio, there are several ways to author regression machine learning models. 
- One way is to use a _visual_ interface called **_designer_** that you can use to train, test, and deploy machine learning models. 
- The **drag-and-drop** interface makes use of clearly defined inputs and outputs that can be **shared**, **reused**, and v**ersion controlled**.
- Each designer project is known as a **pipeline**.

## Evaluate performance
- **Mean Absolute Error (MAE)**: The average difference between predicted values and true values. This value is based on the same units as the label, in this case dollars. The lower this value is, the better the model is predicting.
- **Root Mean Squared Error (RMSE)**: The square root of the mean squared difference between predicted and true values. The result is a metric based on the same unit as the label (dollars). When compared to the MAE (above), a larger difference indicates greater variance in the individual errors (for example, with some errors being very small, while others are large).
- **Relative Squared Error (RSE)**: A relative metric between 0 and 1 based on the square of the differences between predicted and true values. The closer to 0 this metric is, the better the model is performing. Because this metric is relative, it can be used to compare models where the labels are in different units.
- **Relative Absolute Error (RAE)**: A relative metric between 0 and 1 based on the absolute differences between predicted and true values. The closer to 0 this metric is, the better the model is performing. Like RSE, this metric can be used to compare models where the labels are in different units.
- **Coefficient of Determination (R<sup>2</sup>)**: This metric is more commonly referred to as R-Squared, and summarizes how much of the variance between predicted and true values is explained by the model. The closer to 1 this value is, the better the model is performing.
