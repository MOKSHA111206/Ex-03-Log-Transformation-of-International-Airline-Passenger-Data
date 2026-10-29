# Ex-03-Log-Transformation-of-International-Airline-Passenger-Data
## NAME : AMMINENI MOKSHA SREE
## REG NO: 2305001001
## Aim
To perform log transformation on the International Airline Passenger dataset using Python.

## Objectives
1. To load the airline passenger dataset.
2. To visualize the original time series data.
3. To apply log transformation using NumPy.
4. To compare the original and transformed time series.
5. To analyze variance before and after transformation.

## Program
```
    import pandas as pd
    import numpy as np
    import matplotlib.pyplot as plt
    df = pd.read_csv("AirPassengers.csv")
    df["Month"] = pd.to_datetime(df["Month"])
    df.set_index("Month", inplace=True)
    print("Original Data:")
    print(df.head())
    plt.figure(figsize=(10, 5))
    plt.plot(df.index, df["Passengers"])
    plt.title("International Airline Passengers")
    plt.xlabel("Year")
    plt.ylabel("Passengers")
    plt.grid(True)
    plt.show()
    df["Log_Passengers"] = np.log(df["Passengers"])
    print("Log Transformed Data:")
    print(df.head())
    plt.figure(figsize=(10, 5))
    plt.plot(df.index, df["Log_Passengers"])
    plt.title("Log-Transformed Airline Passenger Data")
    plt.xlabel("Year")
    plt.ylabel("Log(Passengers)")
    plt.grid(True)
    plt.show()
    fig, axes = plt.subplots(2, 1, figsize=(10, 8))
    axes[0].plot(df.index, df["Passengers"])
    axes[0].set_title("Original Time Series")
    axes[0].grid(True)
    axes[1].plot(df.index, df["Log_Passengers"])
    axes[1].set_title("Log-Transformed Time Series")
    axes[1].grid(True)
    plt.tight_layout()
    plt.show()
    print("Variance Before Transformation:", df["Passengers"].var())
    print("Variance After Transformation:", df["Log_Passengers"].var())
```
## Output
<img width="641" height="422" alt="image" src="https://github.com/user-attachments/assets/4a20b362-6c46-4d99-b9ad-1fa3fa5ba4ba" />
<img width="1005" height="470" alt="image" src="https://github.com/user-attachments/assets/e3509b1f-14aa-455f-a16f-17cfc6953042" />
<img width="471" height="202" alt="image" src="https://github.com/user-attachments/assets/d818e262-0026-4894-a35e-63d4eb923a67" />
<img width="1010" height="470" alt="image" src="https://github.com/user-attachments/assets/de4cf183-dd46-47a4-a089-1dd407c87b36" />
<img width="1189" height="790" alt="image" src="https://github.com/user-attachments/assets/132dc95b-7e32-4bd3-b424-8915d4a4a55f" />
<img width="547" height="52" alt="image" src="https://github.com/user-attachments/assets/fb8d2766-a1e9-4ee5-9153-cb0196bd46e2" />


## Result
Log transformation was successfully applied to the International Airline Passenger dataset. The original and transformed series were plotted and compared. The transformation compresses larger values and may help stabilize increasing variability.
