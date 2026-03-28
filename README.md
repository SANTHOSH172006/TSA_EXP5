# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 23-03-2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Load the dataset
# Make sure to upload 'heart_rate.csv' to your Colab environment first
data = pd.read_csv('/content/heart_rate.csv')

# Step 2: Select the 'T1' column and handle missing values
X = data['T1'].dropna()

# Step 3: Perform seasonal decomposition
# We use a period of 12 for consistency with the original code,
# as a clear seasonal pattern is not immediately obvious in this data.
decomposition = seasonal_decompose(X, model='additive', period=12)

# Step 4: Plot the decomposition
plt.figure(figsize=(10, 12))

# Original Data Plot
plt.subplot(411)
plt.plot(X, label='Original Data')
plt.legend(loc='upper left')
plt.title('Original Heart Rate Data')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```

### OUTPUT:
<img width="949" height="562" alt="image" src="https://github.com/user-attachments/assets/6b7e9a24-fca6-4fe0-b0db-ebbd4fb960d5" />
<img width="944" height="562" alt="image" src="https://github.com/user-attachments/assets/a568f5d0-97d2-452a-9be4-74245f1ed968" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
