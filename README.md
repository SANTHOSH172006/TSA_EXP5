# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 23/02/26
### Reg No:212223220099

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

# Step 1: Load the dataset, Convert 'date' column to datetime format, Set it as index
data = pd.read_csv('/content/Tesla Dataset.csv', parse_dates=['Date'], index_col='Date') 

# Step 2: Perform seasonal decomposition using the correct column name
decomposition = seasonal_decompose(data['Open'], model='additive', period=12)

# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))  # Adjust the figure size

# Original Data
plt.subplot(411)
plt.plot(data['Open'], label='Open')
plt.legend(loc='upper left')
plt.title('Open Prices')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residuals')

plt.tight_layout()
plt.show()


```






### OUTPUT:

PLOTTING THE DATA:


<img width="1264" height="365" alt="image" src="https://github.com/user-attachments/assets/3c8e8c0f-a5ff-42e3-933e-a95e2779af49" />




TREND PLOT REPRESENTATION :

<img width="1264" height="375" alt="image" src="https://github.com/user-attachments/assets/6913ac5a-6b68-43c8-b0b6-6e626c612e05" />





SEASONAL PLOT REPRESENTATION :

<img width="1778" height="512" alt="image" src="https://github.com/user-attachments/assets/162d5bde-723b-4361-81da-ea48c1c0c910" />




RESIDUAL PLOT:

<img width="1820" height="516" alt="image" src="https://github.com/user-attachments/assets/a9755665-86f9-4247-9bb1-93c34bd1be34" />




### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
