# li-ion-battery-rul-prediction
LSTM neural network for predicting remaining useful life of Li-ion batteries using differential capacity analysis. BEng dissertation project, Lancaster University.

# Li-Ion Battery Remaining Useful Life Prediction

**BEng Third Year Individual Project — Lancaster University**  
Supervisor: Denes Csala · April 2026

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](YOUR_COLAB_LINK_HERE)

---

## Overview

Data-driven prognostic framework for forecasting the Remaining Useful Life (RUL)
of lithium-ion batteries, with a specific focus on predicting the **knee-point** —
the accelerated capacity fade that occurs after a period of gradual decline.

Most traditional methods struggle to predict this critical inflection point accurately.
This project addresses that by combining physics-informed feature engineering with a
deep learning architecture specifically suited to long-range time-series dependencies.

---

## Method

**Data**  
Publicly available cycling datasets: NASA CMAPSS and CALCE.

**Feature Engineering**  
Differential Capacity Analysis (dQ/dV) is used to extract subtle electrochemical
degradation signatures that standard capacity measurements miss.

**Model**  
LSTM (Long Short-Term Memory) Recurrent Neural Network — chosen for its ability
to capture long-term temporal dependencies in battery degradation sequences.

**Pipeline**  
Data cleaning → normalisation → dQ/dV feature extraction → LSTM training
→ evaluation on held-out test batteries

---

## Results

| Metric | Value |
|--------|-------|
| RMSE | < 0.05 Ah |
| MAE | < 0.04 Ah |

The model accurately anticipates the knee-point, confirming the potential of
deep learning frameworks for integration into intelligent Battery Management Systems (BMS).

---

## Libraries

`tensorflow` · `keras` · `pandas` · `numpy` · `scikit-learn` · `matplotlib`

---

## Context

This project sits at the intersection of energy systems and machine learning —
using publicly available data to build a predictive maintenance tool with
direct applications in EV and grid storage reliability.
