# Homework 6 - Case Study 3 Report: Asian Monsoon Flood Risk Index Prediction App
## By: Shaniya Khatua

Kaggle Dataset Link: https://www.kaggle.com/datasets/aliahmadmphil/asian-monsoon-flood-prediction-and-risk-index

Live Shiny Application Link: https://witchystar.shinyapps.io/flood_app/

GitHub Check Code: [ shiny::runGitHub("HW6-CS3-FloodApp_SK", "witchystar") ] (copy what's in the brackets)

### Executive Summary & Problem Framing (Lifecycle Phase 1: Discovery)
Monsoon flooding presents severe socioeconomic risks across Asian regions, causing catastrophic infrastructure damage and displacement. <u>The primary objective of this project is to build an operationalized, interactive predictive data product that models regional Flood Risk Index scores using environmental features.</u>  

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
We implemented **Multiple Linear Regression (Ordinary Least Squares)** to fit a linear relationship between environmental predictors and predicted flood risk severity.

**Mathematical Specification:**
Y = B0 + B1X1 + B2X2 + B3X3 + B4X4 + E
$$Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \beta_3 X_3 + \beta_4 X_4 + \epsilon$$

**Where:**
  - Y = Estimated Flood Risk Index score.
  - B0 = Y-intercept (baseline risk when predictors are zero).
  - B1, B2, B3, B4 = Partial regression coefficients measuring the individual unit effect of Rainfall, Drainage, Deforestation, and Urbanization.
  - E = Residual error term, minimized by OLS: $\sum (Y_i - \hat{Y}_i)^2$

### Algorithm Selection & Mathematical Details (Lifecycle Phase 3 & 4: Model Planning & Building)
IDK
