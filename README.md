# Simulation Study for Underreported Infectious Disease Time Series Models

This repository contains R code developed for a simulation study on infectious disease time series modeling with underreporting. The goal of this study was to assess how well we can estimate key parameters of disease spread, such as infection rates and reporting probabilities, when data is partially observed due to underreporting.


## Project Overview

In infectious disease modeling, underreporting is a common issue where only a fraction of cases are reported. This project simulates time series data for disease cases, "thins" the data to mimic underreporting, and then applies statistical methods to estimate key model parameters:

- **𝜙 (phi)**: The autoregressive parameter representing the dependency of each day's cases on the previous day.

- **𝜈 (nu)**: The baseline infection rate.

- **𝜋 (pi)**: The reporting probability or the fraction of true cases that are observed.

By comparing estimated parameters with the true values used in the simulations, this study provides insights into the reliability of these estimates under various scenarios.


## Files

- **Simulation Code**: *S23 NSERC USRA Simulation Studies for Underreported Infectious Disease Time Series Models (Final).Rmd* — The main R code for generating simulated data, introducing underreporting, estimating parameters, and visualizing results.

- **Results Plots**: The code produces plots showing estimates of 𝜙, 𝜈, and 𝜋 across multiple simulations, helping visualize the accuracy and potential biases in parameter estimates.


## Prerequisites

To run this code, you will need:

- R (version 4.0 or later)

- R packages:

  - ggplot2
  
  - abind
  
  - surveillance

You can install the required packages by running the following in R:

*install.packages(c("ggplot2", "abind", "surveillance"))*


## Running the Code

1. **Load the Code**: Open the R Markdown file *S23 NSERC USRA Simulation Studies for Underreported Infectious Disease Time Series Models (Final).Rmd* in RStudio.

2. **Run the Simulation**: The code will simulate infectious disease time series data, introduce underreporting, estimate model parameters, and generate plots.

3. **View Results**: The plots generated will help you assess the accuracy of the parameter estimates under varying reporting probabilities and time series lengths.


## Code Structure

- **Data Simulation**: The code simulates a time series of true case counts based on a disease transmission model. Each day’s cases depend on the previous day’s cases (captured by 𝜙) and a baseline infection rate (𝜈).

- **Underreporting**: The true cases are "thinned" by a binomial process to introduce underreporting, controlled by the reporting probability, 𝜋.

- **Parameter Estimation**: Using Method of Moments (MoM) estimators, the code estimates values of 𝜙, 𝜈, and 𝜋 based on the underreported data.

- **Visualization**: Plots are generated to show the distribution of estimates for each parameter, comparing them to their true values across various simulation settings.


## Key Results and Interpretation

**Inaccuracy of Moment Estimators for Short Time Series**:

- Estimators of 𝜋, 𝜙, and 𝜈 often perform poorly for short time series, sometimes yielding physically impossible values, such as negative reproduction numbers.

- This underscores the limitations of the Method of Moments for small datasets.


**Effects of Underreporting**:

- Underreporting systematically leads to overestimation of 𝜈, which is counterintuitive.

- The epidemic component's relative importance is underestimated when underreporting is present.


**Behavior of Moment Estimators Across Scenarios**:

- 𝜋: The estimator shows upward bias in the presence of underreporting and performs better for higher true reporting rates.

- 𝜙: Accurately captures the reporting rate (𝜋) and follows a predictable relationship.

- 𝜈: Estimates deviate more significantly as underreporting worsens, reflecting a misattribution of variation in observed counts.


**Visual Insights from the Plots**:

- **Estimates of 𝜙 vs. Estimates of 𝜋**: Clear monotonic relationship, reflecting accurate capture of the reporting rate.

- **Estimates of 𝜈 vs. Estimates of 𝜋**: Non-monotonic pattern with systematic overestimation of 𝜈, peaking at intermediate reporting rates.


## Future Improvements

Potential next steps for this project could include:

- Extending the model to incorporate additional parameters or alternative statistical methods for parameter estimation.

- Applying the methods to real-world infectious disease data to assess the model's performance in practical settings.


## Author

This simulation study was completed as part of an NSERC-funded research project under the supervision of Dr. Justin Slater, focusing on infectious disease modeling with underreporting. The project provided experience in statistical modeling, algorithm development, and debugging in R.
