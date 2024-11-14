# Simulation Study for Underreported Infectious Disease Time Series Models

This repository contains R code developed for a simulation study on infectious disease time series modeling with underreporting. The goal of this study was to assess how well we can estimate key parameters of disease spread, such as infection rates and reporting probabilities, when data is partially observed due to underreporting.


## Project Overview

In infectious disease modeling, underreporting is a common issue where only a fraction of cases are reported. This project simulates time series data for disease cases, "thins" the data to mimic underreporting, and then applies statistical methods to estimate key model parameters:

- φ (phi): The autoregressive parameter representing the dependency of each day's cases on the previous day.

- ν (nu): The baseline infection rate.

- π (pi): The reporting probability or the fraction of true cases that are observed.

By comparing estimated parameters with the true values used in the simulations, this study provides insights into the reliability of these estimates under various scenarios.


## Files

Simulation Code: S23 NSERC USRA Simulation Studies for Underreported Infectious Disease Time Series Models (Final).Rmd — The main R code for generating simulated data, introducing underreporting, estimating parameters, and visualizing results.

Results Plots: The code produces plots showing estimates of φ, ν, and π across multiple simulations, helping visualize the accuracy and potential biases in parameter estimates.


## Prerequisites

To run this code, you will need:

- R (version 4.0 or later)

- R packages:
ggplot2
abind
surveillance

You can install the required packages by running the following in R:

install.packages(c("ggplot2", "abind", "surveillance"))


## Running the Code

Load the Code: Open the R Markdown file simulation_study.Rmd in RStudio.

Run the Simulation: The code will simulate infectious disease time series data, introduce underreporting, estimate model parameters, and generate plots.

View Results: The plots generated will help you assess the accuracy of parameter estimates under varying reporting probabilities and time series lengths.


## Code Structure

Data Simulation: The code simulates a time series of true case counts based on a disease transmission model. Each day’s cases depend on the previous day’s cases (captured by φ) and a baseline infection rate (ν).

Underreporting: The true cases are "thinned" by a binomial process to introduce underreporting, controlled by the reporting probability π.

Parameter Estimation: Using Method of Moments (MoM) estimators, the code estimates values of φ, ν, and π based on the underreported data.

Visualization: Plots are generated to show the distribution of estimates for each parameter, comparing them to their true values across various simulation settings.


## Key Results and Interpretation

Estimates of π (Reporting Probability): Plots show how well the method captures the true reporting rate.

Estimates of φ (Autoregressive Parameter): Visualizations of φ reveal how accurately the model captures the daily dependency of cases, even with underreporting.

Estimates of ν (Mean Infection Rate): The reliability of the baseline infection rate estimate under different reporting probabilities and time series lengths is also examined.

These results can help public health officials and researchers understand the potential biases and reliability of disease model estimates when dealing with underreported data.


## Future Improvements

Potential next steps for this project could include:

Extending the model to incorporate additional parameters or alternative statistical methods for parameter estimation.

Applying the methods to real-world infectious disease data to assess the model's performance in practical settings.


## Author

This simulation study was completed as part of a research project funded by a 2023 NSERC USRA focused on infectious disease modeling with underreporting. The project provided experience in statistical modeling, algorithm development, and debugging in R.
