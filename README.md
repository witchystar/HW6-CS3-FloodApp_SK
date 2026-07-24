# Homework 6 - Case Study 3 Report: Asian Monsoon Flood Risk Index Prediction App
## By: Shaniya Khatua

**Kaggle Dataset Link:** <u>https://www.kaggle.com/datasets/aliahmadmphil/asian-monsoon-flood-prediction-and-risk-index</u>

**Live Shiny Application Link:** <u>https://witchystar.shinyapps.io/flood_app/</u>

**GitHub Check Code ->** shiny::runGitHub("HW6-CS3-FloodApp_SK", "witchystar")

### Executive Summary & Problem Framing (Lifecycle Phase 1: Discovery)
Monsoon flooding poses severe socioeconomic risks across Asia, causing catastrophic infrastructure damage and displacement. <u>The primary objective of this project is to build an operationalized, interactive predictive data product that models regional Flood Risk Index scores using environmental features.</u>  

This application directly addresses key decision-makers defined in the Data Science Lifecycle:
  - **Business Users/Stakeholders:** Regional emergency management teams and municipal civil engineers who require data-driven forecasts for proactive disaster planning and resource allocation.
  - **Data Scientists/Analysts:** Technical stakeholders evaluating feature importance, regression diagnostics, and real-time model behavior.

### Dataset Overview & Data Preparation (Lifecycle Phase 2: Data Prep)
- **Dataset Selected:** Asian Monsoon Flood Prediction and Risk Index (Kaggle).

- **Collected Attributes:**
  - <u>Rainfall Levels (X1):</u> Measure of precipitation intensity during peak monsoon periods.
  - <u>Drainage Capacity (X2):</u> Municipal infrastructure capacity for handling water runoff
  - <u>Deforestation Index (X3):</u> Regional vegetation loss contributing to soil erosion.
  - <u>Urbanization Rate (X4):</u> Impervious surface area percentage.
  - <u>Flood Risk Index (Y):</u> Target dependent metric indicating predicted flood risk severity.

- **Data Conditioning:** Data was cleansed of incomplete records and dynamically scaled. The application enables real-time dynamic train/test splitting (50%–90%) to validate model stability and generalize across different sample sizes.

### Algorithm Selection & Mathematical Details (Lifecycle Phase 3 & 4: Model Planning & Building)
We implemented **Multiple Linear Regression (Ordinary Least Squares)** to model the relationship between environmental predictors and predicted flood risk severity.

**Mathematical Specification:**
$$Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \beta_3 X_3 + \beta_4 X_4 + \epsilon$$

**Where:**
  - $Y$ = Estimated Flood Risk Index score.
  - $\beta_0$ = Y-intercept (baseline risk when predictors are zero).
  - $\beta_1, \beta_2, \beta_3, \beta_4$ = Partial regression coefficients measuring the individual unit effect of Rainfall, Drainage, Deforestation, and Urbanization.
  - $\epsilon$ = Residual error term, minimized by OLS: $\sum (Y_i - \hat{Y}_i)^2$

### Key Empirical Findings & Model Evaluation (Lifecycle Phase 5: Evaluation)
  - **Model Fitness ($R^2$ & Residuals):** Ordinary Least Squares modeling demonstrated a strong goodness-of-fit. Testing on an 80/20 train-test split showed strong correlation between actual and predicted risk scores on the test set visualization.

  - **Primary Drivers:**
    - <u>Rainfall</u> served as the dominant positive driver of flood risk ($\beta_1 > 0$).
    - <u>Drainage Capacity</u> functioned as the primary mitigating factor ($\beta_2 < 0$).

  - **Interactive Scenario Insight:** Using the live app's scenario simulator, decreasing drainage capacity while holding rainfall high leads to an exponential increase in predicted risk levels.

### Deployment & Practical Impact (Lifecycle Phase 6: Operationalize)
The application is fully operationalized and deployed via shinyapps.io

**Recommendations for Disaster Relief Teams:**
  1) **Infrastructure Priority:** Civil planning boards should prioritize expanding municipal drainage capacity, as model outputs indicate it is the most effective operational lever for offsetting heavy monsoon rainfall.
  2) **Scenario Planning:** Municipal planners can utilize the app's interactive sliders to run "what-if" simulations, establishing risk thresholds that trigger early evacuation notices before extreme storm events.
