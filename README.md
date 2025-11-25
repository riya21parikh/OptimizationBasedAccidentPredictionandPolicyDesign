# Optimization-Based Accident Prediction and Prescriptive Policy Design

This repository contains the code and analysis for our project in MIT 15.095, focused on predicting severe traffic accidents in Miami–Dade County and designing optimization-based policies for safety resource allocation. The workflow integrates data cleaning, interpretable machine learning models, and prescriptive analytics.

## Project Overview
We use the US Accidents (March 2023) dataset to build a cleaned, feature-engineered subset for Miami–Dade and train several predictive models for severe-accident classification. Using the best-performing interpretable model (OCT-H), we aggregate predicted risk into a spatial grid and formulate max-coverage optimization models to determine where limited police/EMS units should be deployed.

## Methods

### Prediction
- Logistic Regression  
- Sparse Logistic Regression  
- Optimal Classification Trees (OCT)  
- Optimal Classification Trees with Hyperplanes (OCT-H)  
- Random Forest  
- XGBoost  

OCT-H is selected for prescriptions based on its balance of interpretability and out-of-sample performance.

### Prescription
- Top-K max-coverage model (selects highest-risk grid cells)  
- Radius-based coverage model (units cover cells within R km)  
- Temporal hold-out evaluation (2018–2022 → 2023)

## Key Findings
- Severe-accident risk is highly spatially concentrated.  
- OCT-H provides strong sensitivity and competitive AUC while remaining transparent.  
- Radius-based siting reaches over 90% risk coverage with ~20 well-placed units.  
- Optimized policies outperform random allocation and match or exceed historical hot-spot policies at larger budgets.

## Repository Structure
data/ # Cleaned and processed datasets
predictive modeling/ # End-to-end workflow for predictive models
prescription/ # Optimization models
visualizations/ # Generated figures
ML_Project_Report.pdf # final paper

## Authors
Ayela Chughtai  
Riya Parikh

# **Citation**
If you use or adapt this workflow, please cite the original data sources listed above and reference this repository.
