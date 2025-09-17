# NUE_analysis
# Quantifying Plant Nitrogen Use Efficiency (NUE)

This repository contains the analysis pipeline from my MSc research (University of Alberta, 2019) on **statistical and in-field challenges involved in quantifying crop Nitrogen Use Efficiency (NUE)** in central Alberta.  
All analyses were performed in **R** and focus on comparing ratio-based and regression-based approaches to estimate NUE from geo-referenced wheat yield and soil nitrate data.

---

## 📑 Background

Improving Nitrogen Use Efficiency is critical for sustainable cereal production, but NUE is a complex trait to quantify.  
Chapter 2 of my thesis explored:

* Limitations of the common ratio definition of NUE (grain yield / available soil N).
* Use of alternative regression models (linear, quadratic, piecewise) to estimate NUE more robustly.
* Minimum sample sizes needed to detect meaningful differences between genotypes.

Three study sites were used: **Bert, Brad and Lamoureux** (central Alberta).  
Spring soil samples were collected at 0–15 cm depth using AutoProbe™; grain yield was monitored with a Green Star Monitor 3 combine harvester.

---

## 📂 Repository Structure

nue-analysis/
├── README.md # You’re here
├── LICENSE
├── .gitignore
│
├── data/
│ ├── raw/ # Raw yield and soil nitrate data (if sharable)
│ └── processed/ # Cleaned datasets used for modelling
│
├── scripts/
│ ├── 01_data_cleaning.R # Import & tidy yield + soil data
│ ├── 02_exploratory.R # Descriptive stats & diagnostic tests
│ ├── 03_regression.R # Fit linear, quadratic & piecewise models
│ ├── 04_min_sample_size.R # Sample size calculations
│ └── utils.R # Helper functions
│
├── notebooks/
│ └── NUE_analysis.Rmd # Reproducible report of the full analysis
│
├── results/
│ ├── figures/ # Regression curves, diagnostic plots
│ └── tables/ # Model coefficients & summary tables
│
└── docs/
└── thesis_chapter2.pdf # Original chapter (methods & context)


---

## ⚙️ Methods Summary

* **Data:** Soil nitrate (AN) and wheat grain yield from three central Alberta sites in 2015.
* **Analyses:**  
  * Ratio-based NUE indices.  
  * Linear, quadratic (QR) and piecewise regression (PWR) using `lm()` and custom functions.  
  * Regression diagnostics (residuals, Q-Q plots).  
  * Minimum sample size calculation:  
    \[
    N = \frac{4 \sigma^2 (Z_{crit}+Z_{pwr})^2}{D^2}
    \]
    to detect a 10 % difference in NUE at α = 0.05 and power = 0.8.
* **Software:** R (≥4.0); packages `ggplot2`, `segmented`, `dplyr`, `car`, etc.

---

## 🚀 Getting Started

1. Clone the repo:
   ```bash
   git clone https://github.com/<yourusername>/nue-analysis.git
   cd nue-analysis



install.packages(c("tidyverse","segmented","car"))
source("scripts/01_data_cleaning.R")
source("scripts/02_exploratory.R")
source("scripts/03_regression.R")
source("scripts/04_min_sample_size.R")

Citation

If you use this code, please cite:

Musfira Jamil (2019). Statistical and In-field Challenges Involved in Quantifying Crop Nitrogen Use Efficiency (NUE) and Spatial Soil Fertility in Central Alberta. MSc Thesis, University of Alberta.

