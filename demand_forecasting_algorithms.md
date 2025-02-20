[Back](https://zenjen-devs.github.io)

# Predicting Cost & Demand Fluctuation in Supply Chains

<img src="https://raw.githubusercontent.com/zenjen-devs/zenjen-devs.github.io/master/images/demand_forecasting_banner.png">


[View Repository](https://github.com/zenjen-dev/ml-projects) <br>


*Note: This portfolio section is currently in progress. Please see the project repository linked above for current  status.*

<h3> Project Summary </h3>

In the dynamic and cost-sensitive world of manufacturing, accurately forecasting raw materials costs is critical for maintaining profitability and operational efficiency. This project leverages Facebook's Prophet time series forecasting model to predict raw materials costs, incorporating inflation rate as an exogenous regressor. By analyzing historical production and cost data, the model aims to provide actionable insights for budgeting, procurement, and cost management.

**Results**: The Prophet model achieved a Mean Absolute Error (MAE) of 0.72 and a Root Mean Squared Error (RMSE) of 0.92, indicating moderate predictive accuracy. However, critical model performance metrics Mean Absolute Percentage Error (MAPE) and R² of 0.02 suggest significant challenges in model performance. Current results highlight the need for model refinement and additional feature engineering to maintain model robustness in the future.

<h3> Project Details: Exploratory Data Analysis </h3>

**Data Collection and Preprocessing:**
The dataset used in this project consists of historical production and cost data, including metrics such as production hours, workforce size, machine efficiency, and raw materials costs. The data was sourced from a manufacturing facility and underwent rigorous cleaning, normalization, and preprocessing to ensure accuracy and consistency. Below is a sample visualization of the raw materials cost vs. inflation rate trends over time:
<br>

<img src="https://raw.githubusercontent.com/zenjen-devs/zenjen-devs.github.io/master/images/rawmat_v_inflation.png">
  
Data Source: [Federal Reserve Economic Data](https://fred.stlouisfed.org/)


### Insights from EDA

**Cost Variability:** Raw materials costs exhibit significant variability, with fluctuations driven by factors such as supplier pricing, production volume, and inflation rates.

**Inflation Impact:** The inflation rate shows a strong correlation with raw materials costs, indicating its importance as an exogenous regressor in the forecasting model.

**Production Efficiency:** Metrics such as machine efficiency and production volume per hour show potential relationships with raw materials costs, suggesting opportunities for further feature engineering.

**Seasonal Trends:** While the dataset does not explicitly capture seasonal trends, the inclusion of time-based features (e.g., timestamp hour) may help uncover hidden patterns.
<br>


### Predictive Modeling with Prophet

<img src="https://raw.githubusercontent.com/zenjen-devs/zenjen-devs.github.io/master/images/prophet_fc.png">
<br>
The forecast reflects the seasonal decomposition results that indicate raw materials cost has trended down, with weekly seasonal peaks observed in the last year.

**Model Configuration:**
<br>
Yearly Seasonality: Auto
<br>
Weekly Seasonality: Auto
<br>
Daily Seasonality: Auto
<br>
Exogenous Regressor: Inflation Rate
<br>
Initial Training Period: 90 days
<br>
Cross-Validation Period: 30 days
<br>
Forecast Horizon: 30 days
<br> 
<br> 
<img src="https://raw.githubusercontent.com/zenjen-devs/zenjen-devs.github.io/master/images/prophet_decomp.png">

**Performance Evaluation:**

- MAE (Mean Absolute Error): 0.72

- RMSE (Root Mean Squared Error): 0.92
<br>

**Real-time Monitoring System:**
To operationalize the model, we developed a real-time monitoring dashboard that provides early warnings of potential cost fluctuations. The dashboard integrates with existing procurement and budgeting systems, enabling stakeholders to take proactive measures such as adjusting procurement strategies or renegotiating supplier contracts.

**Integration with Maintenance Protocols:**
Upon successful validation, the model was integrated into the company's procurement and budgeting protocols. Key outcomes include:

- Proactive Cost Management: Early detection of potential cost fluctuations allows for timely interventions, reducing the likelihood of budget overruns.

- Optimized Procurement Strategies: By forecasting raw materials costs, the model helps optimize procurement strategies, ensuring cost-effective sourcing.

- Enhanced Supplier Negotiations: Cost forecasts enable more effective negotiations with suppliers, ensuring favorable terms and pricing.

**References:** [See Repository](https://github.com/zenjen-dev/deep-learning_predicting-failures/blob/main/DeepLearning_PredictiveMaintenance.ipynb) 
