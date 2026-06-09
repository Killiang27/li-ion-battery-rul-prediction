# li-ion-battery-rul-prediction
LSTM neural network for predicting remaining useful life of Li-ion batteries using differential capacity analysis. BEng dissertation project, Lancaster University.

# Li-Ion Battery Remaining Useful Life Prediction
**BEng Third Year Individual Project — Lancaster University**  
Supervisor: Denes Csala · April 2026

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1WGi96f8jgrBT6gio2NfmHA9ACX8ZV0A-?usp=drive_link)

> ⚠️ **Academic Project — Not for Deployment**  
> This is a university dissertation project built to explore deep learning for battery prognostics. It is not a certified prognostic tool and should not be integrated into real Battery Management Systems, EV platforms, or grid storage applications without independent validation.

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
Publicly available cycling datasets: NASA, Stanford/MIT and CALCE.

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

## Reproducing This Project

**Datasets**  
This notebook uses three publicly available battery cycling datasets:

| Dataset | Source | Link |
|---------|--------|------|
| NASA PCoE | NASA Prognostics Center | [data.nasa.gov](https://data.nasa.gov/dataset/Li-ion-Battery-Aging-Datasets/uj5r-zjdb) |
| Stanford/MIT | MIT Battery Data | [data.matr.io](https://data.matr.io/1/) |
| CALCE | University of Maryland | [calce.umd.edu](https://calce.umd.edu/battery-data) |

**To run the notebook yourself:**

1. Download the datasets from the links above
2. Upload them to your own Google Drive
3. Mount your Drive in Colab:  
   `from google.colab import drive; drive.mount('/content/drive')`
4. Update the file path variable near the top of the notebook to match your own Drive structure:

```python
base_folder = '/content/drive/MyDrive/YOUR_FOLDER/battery_data/'
```

> The paths in the current notebook point to the author's private Drive and will not work without this change.

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
