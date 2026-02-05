# RNP CT-MON Route Change Detection Challenge

Second place solution for the RNP Data Challenge 2025, focused on detecting network route changes in traceroute data from Brazil's national research and education network.

## Overview

This project addresses the problem of automatically detecting when network routes change between monitored endpoints. The RNP (Rede Nacional de Ensino e Pesquisa) operates CT-MON, a monitoring system that tracks network behavior across Brazil's academic infrastructure. Route changes can indicate failures, load balancing events, or routing reconfigurations, making their detection critical for network operations.

The challenge presented a highly imbalanced binary classification problem with approximately 20 million training samples, where only 1.85% represented actual route changes.

## Problem Statement

The dataset consists of traceroute measurements between various source-destination pairs. Each record includes RTT values, probe statistics, and timestamps. The task is to predict whether the network route changed between consecutive measurements for the same source-destination pair.

The main difficulty stems from the severe class imbalance (53:1 ratio) combined with noisy RTT data that naturally varies even when routes remain stable. Additionally, different network paths exhibit different baseline behaviors, requiring features that generalize across heterogeneous routes.

## Repository Structure

The repository contains two notebooks. The file `rnp-route-change-detection-analysis.ipynb` is a cleaned, documented version suitable for presentation and reference. The original `explore-rnp-data-challenge-2025.ipynb` contains the working exploration and can be removed if not needed.

## Installation and Usage

The code requires Python 3.10 or higher with standard data science libraries. Install dependencies with:

```bash
pip install numpy pandas matplotlib seaborn xgboost scikit-learn jupyter
```

The notebook was developed on Kaggle and expects data in the `/kaggle/input/data-challenge-2025-rnp/` directory structure. For local execution, adjust the data paths accordingly.

To run the analysis:

```bash
jupyter notebook rnp-route-change-detection-analysis.ipynb
```

The notebook follows a linear workflow from data loading through feature engineering, model training, evaluation, and test set prediction. All cells can be run sequentially.

## Technical Dependencies

- **NumPy** and **Pandas**: Data manipulation and numerical computing
- **XGBoost**: Gradient boosting classifier implementation
- **scikit-learn**: Train-test splitting, metrics, and evaluation utilities
- **Matplotlib** and **Seaborn**: Visualization and plotting