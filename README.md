# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 


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

# Step 1: Load dataset, convert 'Date' column to datetime, set a
data = pd.read_csv("tsa.csv", parse_dates=['Date'], index_col='Date')

# Step 2: Perform seasonal decomposition on 'Close' prices
# Using period=30 (approx monthly seasonality for daily stock data)
decomposition = seasonal_decompose(data['Close'], model='additive', period=30)

# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(data['Close'], label='Close')
plt.legend(loc='upper left')
plt.title('Closing Prices')

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




## PLOTTING THE DATA:
<img width="1035" height="291" alt="image" src="https://github.com/user-attachments/assets/2e5ccd1d-e4fd-49da-bcf7-1bd76808e060" />


## SEASONAL PLOT REPRESENTATION :
<img width="1012" height="299" alt="image" src="https://github.com/user-attachments/assets/19fd41cb-2099-4181-8fc3-f8268a010bee" />




## TREND PLOT REPRESENTATION :
<img width="1023" height="306" alt="image" src="https://github.com/user-attachments/assets/eaf717dd-4f8c-4e83-be21-cf106501270e" />


## OVERAL REPRESENTATION:
<img width="1093" height="294" alt="image" src="https://github.com/user-attachments/assets/89ee1bce-b38d-4ee7-807e-6b45628eba6c" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
