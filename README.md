# Ex.No: 03 COMPUTE THE AUTO FUNCTION(ACF)
#### Date: 
#### Name : Syed Abdul Wasih H
#### Reg no: 212221240057

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import numpy as np
import pandas as pd
import statsmodels.api as sm
import matplotlib.pyplot as plt

np.random.seed(42)  # For reproducibility
data = np.random.normal(loc=150, scale=70, size=50)

# Mean
data_mean = np.mean(data)

# Variance
data_var = np.var(data)

# Normalized data
normalized_data = (data - data_mean) / np.sqrt(data_var)

# Compute the autocorrelation function (ACF)
acf_result = np.correlate(normalized_data, normalized_data, mode='full')

# Take only the positive lags
acf_result = acf_result[len(acf_result)//2:]

# Plot the ACF
plt.figure(figsize=(10, 5))
plt.stem(acf_result[:36], use_line_collection=True)
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.title('Autocorrelation Function (ACF)')
plt.show()
```
### OUTPUT:
![time5](https://github.com/Vishwarathinam/TSA_EXP3/assets/95266350/47c5b475-dd4e-4162-9c3b-ff740838078c)


### RESULT:
Thus we have successfully implemented the auto correlation function in python.
