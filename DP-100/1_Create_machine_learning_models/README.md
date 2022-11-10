# Explore and analyze data with Python
```python
# List
data = [50,50,47,97,49,3,53,42,26,74,82,62,37,15,70,27,36,35,48,52,63,64]
print(data)

# Numpy array
import numpy as np

grades = np.array(data)
print(grades)

print (type(data),'x 2:', data * 2)
print('---')
print (type(grades),'x 2:', grades * 2)
```
- Note that multiplying a list by 2 creates a new list of twice the length with the original sequence of list elements repeated. 
- Multiplying a NumPy array on the other hand performs an element-wise calculation in which the array behaves like a _vector_, so we end up with an array of the same size in which each element has been multiplied by 2.
- [Explore data with NumPy and Pandas](https://learn.microsoft.com/en-us/training/modules/explore-analyze-data-with-python/3-exercise-explore-data)

### Measures of central tendency
To understand the distribution better, we can examine so-called _measures of central tendency_; which is a fancy way of describing statistics that represent the "middle" of the data. The goal of this is to try to find a "typical" value. Common ways to define the middle of the data include:
- The mean: A simple average based on adding together all of the values in the sample set, and then dividing the total by the number of samples.
- The median: The value in the middle of the range of all of the sample values.
- The mode: The most commonly occuring value in the sample set. (Of course, in some sample sets , there may be a tie for the most common value - in which case the dataset is described as _bimodal_ or even _multimodal_.)
- [Visualize data with Matplotlib](https://learn.microsoft.com/en-us/training/modules/explore-analyze-data-with-python/5-exercise-visualize-data)
