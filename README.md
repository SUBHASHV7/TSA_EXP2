# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
### NAME: SUBHASH V
### REG.NO: 212224240163
### Date:04-11-2026

### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program
### PROGRAM:
A - LINEAR TREND ESTIMATION
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("/content/Indian_Climate_Dataset_2024_2025.csv")

# many cities per date, so pick one city
df = df[df['City'] == 'Chennai']
df['Date'] = pd.to_datetime(df['Date'])

# x = day number (1, 2, 3, ...), y = average temperature
x = np.arange(1, len(df) + 1)
y = df['Temperature_Avg (°C)'].values

m, c = np.polyfit(x, y, 1)
trend = m * x + c

plt.figure(figsize=(12, 5))
plt.plot(df['Date'], y, label='Original Data', color='lightgray')
plt.plot(df['Date'], trend, label='Linear Trend', color='red')
plt.title('Linear Trend Estimation (Chennai)')
plt.xlabel('Date')
plt.ylabel('Temperature (°C)')
plt.legend()
plt.grid(True)
plt.show()

print("Slope (m):", m)
print("Intercept (c):", c)
print("First 5 Linear Trend Values:", trend[:5])
```
B- POLYNOMIAL TREND ESTIMATION
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("/content/Indian_Climate_Dataset_2024_2025.csv")

# many cities per date, so pick one city
df = df[df['City'] == 'Chennai']
df['Date'] = pd.to_datetime(df['Date'])

# x = day number (1, 2, 3, ...), y = average temperature
x = np.arange(1, len(df) + 1)
y = df['Temperature_Avg (°C)'].values

coeff = np.polyfit(x, y, 2)
trend = np.polyval(coeff, x)

plt.figure(figsize=(12, 5))
plt.plot(df['Date'], y, label='Original Data', color='lightgray')
plt.plot(df['Date'], trend, label='Polynomial Trend', color='red')
plt.title('Polynomial Trend Estimation (Chennai)')
plt.xlabel('Date')
plt.ylabel('Temperature (°C)')
plt.legend()
plt.grid(True)
plt.show()

print("Coefficients:", coeff)
print("First 5 Polynomial Trend Values:", trend[:5])
```
### OUTPUT
A - LINEAR TREND ESTIMATION

<img width="996" height="470" alt="download" src="https://github.com/user-attachments/assets/946b7c8c-a139-4c77-8851-12dd87448916" />


B- POLYNOMIAL TREND ESTIMATION

<img width="996" height="470" alt="download" src="https://github.com/user-attachments/assets/6bdcb1ea-7483-4278-926e-d5f04854684a" />


### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
