# Towards-Optimal-BMS-Design-LSTM-Based-State-of-Health-Estimation-from-Raw-Operational-Data

State of Health (SoH) is one of the key indicators of lithium-ion battery performance, defined as the ratio of the remaining capacity to the initial nominal capacity. Accurate SoH estimation is crucial for Battery Management Systems (BMS), ensuring reliability, safety, and timely replacement of batteries in electric vehicles and other applications.

This repository contains the implementation of experiments on SoH prediction using the **NASA Prognostics Center of Excellence dataset**. The dataset includes cycling data of lithium-ion cells with nominal capacity of 2 Ah, providing measurements such as voltage, current, temperature, capacity, and time across charge/discharge cycles. 

In addition to raw BMS data, we also tested features derived from **Incremental Capacity Analysis (ICA)**. ICA is a common diagnostic technique where the derivative of capacity with respect to voltage (dQ/dV) is analyzed to extract degradation-sensitive features such as peak value, peak position, and area under the curve.


#### ICA example:

![ICA example](images/ica_example.png)

We compare two machine learning models:
- **Gradient Boosting Trees (GBT)**
- **Long Short-Term Memory (LSTM) networks**

#### LSTM network

![LSTM network](images/lstm1.png)


### Results
- **LSTM on raw BMS data** achieved the best accuracy with **RMSE = 1.27**, clearly outperforming all other approaches.  
- Adding ICA features to LSTM degraded performance (**RMSE = 1.71**).  
- GBT on ICA features performed moderately (**RMSE = 2.78**), but all GBT-based approaches lagged behind LSTM.  
- Combining raw data with ICA or hybrid GBT+LSTM methods did not yield improvements, often worsening results.  


---

##  References
- Dataset: [NASA Prognostics Data Repository](https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/#battery$0)  


