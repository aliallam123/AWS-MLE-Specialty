# Time Series Analysis - Must Know for MLE exam

- Time series = data points collected over time (usually discrete time steps)  
- Key components of time series:  
  - **Trend**: long-term increase or decrease (e.g. sea level rising over years)  
  - **Seasonality**: repeating patterns at fixed intervals (e.g. monthly flu cases peaking in winter)  
  - **Noise**: random fluctuations that cant be explained by trend or seasonality  

- Time series can have:  
  - Trend only  
  - Seasonality only  
  - Both trend + seasonality  

- Models to represent time series:  
  - **Additive model**:  
    - time series = trend + seasonality + noise  
    - Use when seasonal effect is roughly constant regardless of trend level  
  - **Multiplicative model**:  
    - time series = trend * seasonality * noise  
    - Use when seasonal variation scales with trend (amplitude changes as level changes)  

- In EDA, identify trend and seasonality to better understand & model data  

*Know these basics to interpret time series and choose preprocessing/modeling approach.*
