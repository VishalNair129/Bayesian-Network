# Bayesian Network Analysis of Pollution, Climate, and Health Data

This repository contains an implementation of a **Bayesian Network (BN) model** to analyze the relationships between **air pollution, climate conditions, and health outcomes** in English regions. The project reproduces the methodology from:

> **Vitolo et al. (2018)** - *Modeling Air Pollution, Climate, and Health Data Using Bayesian Networks: A Case Study of the English Regions*, *Earth and Space Science*.

## 📌 Project Overview
This project aims to **replicate and validate** the study using **bnlearn** in R by constructing a **Bayesian Network** that captures dependencies among environmental and health-related variables. The model incorporates **structural learning, missing data imputation, and validation** techniques.

## 🚀 Key Features
- **Structural Learning**: Combined **top-down (expert knowledge)** and **bottom-up (data-driven)** approaches using **Hill Climbing** with **BIC scoring**.
- **Missing Data Imputation**: Used **Structural Expectation-Maximization (SEM)** for imputing missing values.
- **Model Validation**: Evaluated with **Normalized Root Mean Squared Error (NRMSE)**.
- **Graphical Representation**: Visualized **Directed Acyclic Graph (DAG)** using **graphviz**.

## 📊 Dataset
The dataset consists of **air quality, meteorological, and health records** from:
- **DEFRA (UK Department for Environment, Food, and Rural Affairs)** – Pollution and air quality data.
- **ERA-Interim (European Centre for Medium-Range Weather Forecasts)** – Climate reanalysis dataset.
- **Office for National Statistics (ONS, UK)** – Mortality and health records.

## 🔧 Implementation Steps
1. **Preprocessing**:
   - Sampled **1%** of the dataset for efficient computation.
   - Defined **blacklist constraints** to prevent unrealistic causal links.

2. **Bayesian Network Learning**:
   - **Structural EM** for missing data imputation.
   - **Hill Climbing with BIC scoring** for DAG learning.

3. **Model Validation**:
   - Computed **NRMSE** for each numeric feature in training and test datasets.
   - Compared results with the **original study**.

4. **Graphical Representation**:
   - Visualized DAG structure using **graphviz.plot()**.
   - Compared **our DAG structure** with the **original paper's DAG**.

## 📈 Results and Observations
- The BN model captured **key dependencies** among air pollutants, weather conditions, and health variables.
- **NRMSE analysis** revealed **missing predictions** in variables such as **CVD60, NO₂, O₃, SO₂, PM₁₀, and CO**, likely due to limited data in the **1% test subset**.
- The DAG structure aligns well with atmospheric chemistry and health impact literature.

## ⚠️ Limitations
- **Time variables (Day, Month, Hour) were categorical**, which may affect temporal trend detection.
- **1% dataset sampling** limits robustness of validation.
- Some features had **sparse data availability**, affecting accuracy for certain health outcomes.

## 🔮 Future Work
- Expand dataset sampling beyond **1%** for better validation.
- Optimize DAG structure by incorporating **domain-specific constraints**.
- Experiment with **alternative Bayesian Network algorithms**.


