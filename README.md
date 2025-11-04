# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# Date:7/10/25
### Name:Kishore N
### Reg: 212223230106


### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')

# Load the dataset
data = pd.read_csv('gold_price_data.csv', nrows =200)

# Use the 'Close' price column
close_prices = data['Value'].dropna()

plt.rcParams['figure.figsize'] = [10, 7.5]

# Simulate ARMA(1,1) Process
ar1 = np.array([1, 0.33])
ma1 = np.array([1, 0.9])
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(close_prices))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(1,1)
plot_acf(ARMA_1)
plot_pacf(ARMA_1)

# Simulate ARMA(2,2) Process
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(close_prices) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(2,2)
plot_acf(ARMA_2)
plot_pacf(ARMA_2)

```

# OUTPUT:
### SIMULATED ARMA(1,1) PROCESS:
<img width="838" height="643" alt="download" src="https://github.com/user-attachments/assets/79b8b336-9d77-4a99-8b75-384f07b0dab0" />


### Partial Autocorrelation:

<img width="847" height="643" alt="download" src="https://github.com/user-attachments/assets/bf62687d-8577-4b39-82d2-aa0cf21bff93" />

### Autocorrelation:
<img width="847" height="643" alt="download" src="https://github.com/user-attachments/assets/882e19a1-8537-4f67-9385-3a88d4e12270" />

### SIMULATED ARMA(2,2) PROCESS:
<img width="860" height="643" alt="download" src="https://github.com/user-attachments/assets/da2a45e5-e253-4d40-aa62-81edc7ea1cea" />

### Partial Autocorrelation


<img width="847" height="643" alt="download" src="https://github.com/user-attachments/assets/1cf57b92-7d11-45e5-bcde-cfa549b6a97f" />


### Autocorrelation:

<img width="847" height="643" alt="download" src="https://github.com/user-attachments/assets/fa29d05a-35bb-4717-9140-3fc85cddc79c" />

# RESULT:
Thus, a python program is created to fir ARMA Model successfully.
