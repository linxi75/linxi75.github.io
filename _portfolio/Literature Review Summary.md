
---
title: "Research Summary"
excerpt:""Practicum Project Literature Review" 
collection: portfolio
---

**Topic: Time series forecasting for precipitation/rainfall**

**Relevant Research Paper \#1** : *Time Series Analysis Model for Rainfall Data in Jordan: Case Study for Using Time Series Analysis*

Full citation

**Naill, P. E., & Momani, M. (2009).** Time Series Analysis Model for Rainfall Data in Jordan: Case Study for Using Time Series Analysis. *American Journal of Environmental Sciences, 5*(5), 599-604. [https://doi.org/10.3844/ajessp.2009.599.604](https://doi.org/10.3844/ajessp.2009.599.604)

Main objective of the research

To develop an ARIMA model for forecasting monthly rainfall in Amman, Jordan, and assist water resource management.

Methods and approaches used 

This study applied the Box-Jenkins methodology to develop an ARIMA model for rainfall forecasting. The process involved three main steps: Model Identification, Parameter Estimation, and Diagnostic Checking. First, the authors assessed stationarity using ACF/PACF plots, identified seasonal patterns, and applied seasonal differencing (D=1) to remove them. They initially proposed SARIMA(1,0,1)(1,1,1)₁₂, but after testing t-values, correlation matrices, and SSR, they finalized SARIMA(1,0,0)(0,1,1)₁₂, capturing a 12-month seasonal cycle. Residual analysis and a Chi-Square Test confirmed that errors resembled white noise, validating the model’s adequacy for capturing seasonal rainfall trends.

Key findings and results 

The model effectively captured seasonal rainfall patterns, confirming Jordan's 12-month cycle. It identified last year’s rainfall and last month’s rainfall as key predictors. The 10-year forecast showed no clear decreasing trend, suggesting no strong evidence of declining rainfall. While the model performed well for seasonal patterns, it had high errors in monthly predictions and struggled to capture extreme rainfall events, limiting its usefulness for cloudburst forecasting.

Performance metrics reported

The paper reports SSR=737,593 and RMSE=28.1mm, indicating high errors in monthly predictions, especially for extreme rainfall. A Chi-square test confirmed white noise residuals, validating the model. Key parameters were statistically significant (φ₁=4.4, γ₁=44.8), reinforcing the model’s reliability for seasonal forecasting.

Data sources and features used

The study used monthly rainfall data (1922–1999, 936 observations) from Amman Airport, provided by the Jordan Meteorological Department. The dataset shows strong seasonality (most rainfall from December to March) but lacks meteorological variables like temperature or humidity, relying solely on historical rainfall trends.

Limitations and challenges identified 

The ARIMA (1,0,0)(0,1,1)₁₂ model captured seasonal patterns but struggled with extreme rainfall events, limiting its use for cloudburst forecasting. It assumes linear relationships, relies solely on historical data (1922–1999), and lacks external climate factors, making it less effective for long-term and contemporary climate predictions.

Relevance to our project

This paper provides a strong foundation for SARIMA-based rainfall forecasting but highlights its limitations in predicting extreme events, crucial for cloudburst forecasting. Its limitations underscore the need for hybrid models integrating machine learning and meteorological factors to develop a more robust early warning system for urban cloudbursts.Leveraging these insights, we can refine, improve, and combine different modeling approaches to develop a more robust early warning system for urban cloudbursts.  
**Relevant Research Paper \#2** :  *Prediction of Rainfall Time Series Using the Hybrid DWT-SVR-Prophet Model*

Full citation

**Li, D., Ma, J., Rao, K., Wang, X., Li, R., Yang, Y., & Zheng, H. (2023).** *Prediction of Rainfall Time Series Using the Hybrid DWT-SVR-Prophet Model.* Water, 15(10), 1935\. [https://doi.org/10.3390/w15101935](https://doi.org/10.3390/w15101935)

Main objective of the research

To develop a hybrid machine learning model (DSP) that integrates Discrete Wavelet Transform, Support Vector Regression, and Prophet to improve rainfall prediction accuracy by decomposing time series into frequency-based components

Methods and approaches used 

This study proposed the DSP model (DWT-SVR-Prophet) for rainfall prediction. Authors first normalized the data and confirmed no missing values. Then, a 3-level Discrete Wavelet Transform (DWT) decomposed rainfall into high-frequency (sharp spikes) and low-frequency (seasonal trends) components. SVR predicted high-frequency variations, while Prophet modeled low-frequency component, capturing long-term seasonal trends. Grid Search optimized SVR and Prophet hyperparameters, while DWT parameters were based on prior research. Finally, SVR and Prophet outputs were combined to reconstruct the final rainfall forecast.

Key findings and results 

The DSP model outperformed traditional models, achieving lower errors and higher accuracy in rainfall prediction. It had an RMSE of 6.17 and R² of 0.75 ,representing lower errors and stronger correlations with actual rainfall comparably.  It improved peak rainfall prediction by reducing RMSE by 46.3% and MAE by 55.9% over SSP. Combining DWT with SVR and Prophet enhances forecasting accuracy, especially in capturing extreme weather.

Performance metrics reported

The paper evaluated performance using Root Mean Square Error, Mean Absolute Error, and the coefficient of determination. DSP had the lowest RMSE (6.17) and MAE (3.29) and the highest R² (0.75), outperforming SSP, SVR, and Prophet. These metrics confirm DSP’s superior accuracy in capturing both short-term spikes and long-term trends, showing significant outperformance than traditional models.

Data sources and features used

The study used rainfall data from five meteorological stations in China (2014–2016), obtained from the National Weather Science Data Center. The data was normalized, no missing values found. The study focused on time series features, with DWT extracted high and low frequency components, which trained SVR for short-term spikes and Prophet for seasonal trends.

Limitations and challenges identified 

The paper highlights three key limitations of the DSP model: (1) DWT parameters were predefined, not dynamically tuned, (2) accuracy dropped in areas with place with sparse rainfall data (R² \= 0.32), and (3) high computational cost of DSP and processing power due to DWT decomposition and hyperparameter tuning.

Relevance to our project

This paper is highly relevant to our cloudburst early warning system project, as it demonstrates an effective hybrid forecasting model (DSP: DWT-SVR-Prophet). DWT separates short-term cloudbursts from long-term trends, essential for short-window extreme weather forecasting. SVR captures sudden rainfall spikes, while Prophet models seasonal variations. Adapting this approach with real-time weather data could enhance cloudburst prediction accuracy, improving disaster preparedness and response strategies in urban areas.

Brief synthesis:

Methods Applied 

ARIMA is unsuitable for our project as it assumes linearity and struggles with extreme rainfall events. Instead, we can adapt a hybrid approach like DSP (DWT-SVR-Prophet), which effectively handles both short-term rainfall spikes and long-term seasonal trends, making it particularly useful for urban extreme rainfall forecasting.

To further refine cloudburst prediction, we can consider testing alternative decomposition techniques beyond DWT, such as Empirical Mode Decomposition and Variational Mode Decomposition. EMD is more flexible than DWT for non-stationary rainfall patterns, which could be beneficial for irregular rainfall trends. VMD  is similar to EMD but more robust to noise, making it effective for highly fluctuating weather data. 

Additionally, we can apply hyperparameter optimization to improve model performance.Given Mumbai’s proximity to the Arabian Sea, we should integrate wind speed and humidity as external variables to enhance our prediction model. By leveraging a hybrid modeling framework, advanced decomposition techniques, hyperparameter optimization, and external meteorological influences, we can develop a more accurate early warning system for cloudbursts in Mumbai.

Challenges 

We should anticipate high computational costs from hybrid models, especially with extensive hyperparameter tuning, which demands large processing power. The lack of sufficient data may affect prediction accuracy as seen in Study 2\. Relying solely on historical rainfall data could further reduce model effectiveness in rapidly changing urban climates.

Sata sources/Features consider

We should obtain data from highly credible sources, particularly IMD (India Meteorological Department), which provides real-time and historical rainfall, temperature, wind speed, and humidity data. Collecting data from multiple meteorological stations across India with varying climate conditions will improve model generalizability. To ensure consistency, normalizing data across stations is essential. Key features include precipitation, the core predictor of cloudburst events; humidity, as high levels often precede heavy rainfall; and wind speed, since strong vertical winds can intensify cloud formation.

### 

