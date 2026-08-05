*Read this in other languages: [Español](README_es.md)*
# Deep Learning Project — Predictive Maintenance for Turbofan Engines (NASA C-MAPSS)

## Overview

This project develops an advanced **Deep Learning benchmark for Predictive Maintenance** using the **NASA C-MAPSS (Commercial Modular Aero-Propulsion System Simulation)** dataset.

Instead of predicting the exact **Remaining Useful Life (RUL)** through regression, the problem is reformulated as a **multiclass multivariate time series classification task**, where engine health is categorized into operational risk levels.

The solution evaluates and compares **five State-of-the-Art Deep Learning architectures** for multivariate time series classification, implemented in **PyTorch** following an end-to-end industrial machine learning workflow.

---

#  About the Dataset

**Dataset:** Turbofan Engine Degradation Simulation Dataset (C-MAPSS)

**Source:** NASA Prognostics Data Repository

---

# General Description

The C-MAPSS dataset simulates the degradation process of turbofan aircraft engines operating under different environmental conditions and fault modes.

Each engine is monitored through multiple sensor channels that capture its thermodynamic behavior over time until failure.

The dataset contains:

* Operational settings
* Sensor measurements
* Engine identifiers
* Complete degradation trajectories


---

# Problem Reformulation

Instead of predicting the exact Remaining Useful Life (RUL), the problem is transformed into a multiclass classification task.

Engine health states are defined as follows:

| Class    | Remaining Useful Life |
| -------- | --------------------- |
| Healthy  | > 60 cycles           |
| Warning  | 30–60 cycles          |
| Critical | < 30 cycles           |

This formulation provides more actionable outputs for maintenance planning and industrial decision-making.

---

#  Feature Engineering

The project includes extensive feature engineering techniques designed to enhance degradation pattern detection.

 -  Dynamic Features
 -  Static Features
 -  Data Preparation

---

#  Data Leakage Prevention

A critical aspect of predictive maintenance projects is preventing information leakage.

To ensure realistic evaluation:

* Entire engine trajectories remain in a single split.
* Group-based Train/Validation/Test partitioning.
* No future information is used during feature generation.
* RUL values are removed after target construction.

---

#  Deep Learning Architectures Evaluated

Five advanced architectures were implemented and benchmarked.

## 1. FCN (Fully Convolutional Network)

Traditional strong baseline for time series classification.

---

## 2. InceptionTime

State-of-the-Art convolutional architecture for time series classification.

---

## 3. Time Series Transformer

Transformer-based architecture using self-attention.

---

## 4. PatchTST

Recent State-of-the-Art Transformer architecture.

---

## 5. ConvTransformer

Hybrid CNN-Transformer architecture.

---

#  Training Strategy

The training pipeline includes:

* PyTorch Implementation
* GPU Acceleration
* Early Stopping
* Gradient Clipping
* Class Weight Balancing
* Adam Optimizer
* CrossEntropy Loss

---

#  Generated Outputs

The project automatically produces:

*  Benchmark Comparison Table
*  Accuracy Comparison
*  Macro F1 Comparison
*  Training Time Comparison
*  Confusion Matrix
*  Classification Report
*  ROC Curves
*  Engine Degradation Visualizations
*  Best Model Identification

---

#  Business Impact

This solution can support:

* Predictive Maintenance Scheduling
* Aircraft Fleet Management
* Spare Parts Planning
* Downtime Reduction
* Failure Prevention
* Asset Health Monitoring

The multiclass approach provides interpretable maintenance alerts directly usable by operational teams.

---

#  License

This project is intended for educational, research, and portfolio purposes.

Dataset provided by NASA Ames Research Center.

---

## Author

**Armando Guarnera**
Data Scientist
Argentina