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
Note that multiplying a list by 2 creates a new list of twice the length with the original sequence of list elements repeated. Multiplying a NumPy array on the other hand performs an element-wise calculation in which the array behaves like a vector, so we end up with an array of the same size in which each element has been multiplied by 2.
