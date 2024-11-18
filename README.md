# Code for "Measuring Name Concentrations through Deep Learning"

## Authors
**Eva Lütkebohmert**, **Julian Sester**

---

## Abstract
We propose a novel deep learning approach for quantifying name concentration risk in loan portfolios, designed specifically for small portfolios. This approach accommodates both actuarial and mark-to-market definitions of loss. Our neural network training relies on Monte Carlo simulations with importance sampling, which we explicitly formulate for both the CreditRisk+ and ratings-based CreditMetrics models. Numerical results using simulated and real data demonstrate the accuracy of our approach and its superior performance compared to existing analytical methods for name concentration risk assessment in small, concentrated portfolios.

---

## Preprint
The full paper is available on [arxiv](https://arxiv.org/abs/2403.16525).

---

## Table of Contents

The repository includes the following notebooks and Python files:

### 1. Creation of Scenarios
- Monte Carlo simulation notebooks for scenario generation:
  - [Create_Scenarios_MtM.ipynb](Create_Scenarios_MtM.ipynb): Mark-to-Market case
  - [Create_Scenarios_actuarial.ipynb](Create_Scenarios_actuarial.ipynb): Actuarial case

### 2. Neural Network Training
- Training notebooks for the First order GA approximations (needed as input to the neural networks_:
  - [Compute_GA_approx_MtM.ipynb](Compute_GA_approx_MtM.ipynb): Mark-to-Market case
  - [Compute_GA_approx_actuarial.ipynb](Compute_GA_approx_actuarial.ipynb): Actuarial case
- Training notebooks for the training of the neural networks:
  - [Training_NN_MtM.ipynb](Training_NN_MtM.ipynb): Mark-to-Market case
  - [Training_NN_actuarial.ipynb.ipynb](Training_NN_actuarial.ipynb): Actuarial case
- Python code files:
  - [MtM_training.py](MtM_training.py): Mark-to-Market case
  - [actuarial_training.py](actuarial_training.py): Actuarial case
 

### 3. Auxiliary Functions
- Helper functions for the project:
  - [IS_misc_functions.py](IS_misc_functions.py)
  - [misc_functions.py](misc_functions.py)

### 4. Sensitivity Analysis
- Sensitivity analysis notebooks:
  - [Sensitivities_mtm.ipynb](Sensitivities_mtm.ipynb): Mark-to-Market case
  - [Sensitivities_actuarial.ipynb](Sensitivities_actuarial.ipynb): Actuarial case

### 5. Evaluation with Real MDB Portfolios
- Portfolio evaluation:
  - [Portfolio_Evaluation.ipynb](Portfolio_Evaluation.ipynb): Evaluation notebook
  - [MDB portfolios.xlsx](MDB portfolios.xlsx): MDB portfolio data
  - [transition_matrix_RC.csv](transition_matrix_RC.csv) & [transition_matrix_SP.csv](transition_matrix_SP.csv): Transition matrices
  - [probs.txt](probs.txt): S&P matrix probabilities

### 6. Stress Testing
- Mark-to-Market case: [Stress_Testing_MtM.ipynp](Stress_Testing_MtM)
- Actuarial case: [Stress_Testing_actuarial.ipynp](Stress_Testing_actuarial)

### 7. Miscellaneous Files
- Scalers for neural networks:
  - [scaler_actuarial.gz](scaler_actuarial.gz): Actuarial neural network scaler
  - [scaler_mtm.gz](scaler_mtm.gz): MtM neural network scaler

---

## Features
Our approach provides the following main features
- **Training neural networks**: Supports underlying actuarial (CreditRisk+) and mark-to-market (CreditMetrics) framework, allowing for the extremely fast computation of granularity adjustments based on credit portfolio characteristics, given as an input to neural networks.
- **Sensitivity analysis**: Allows to study , post-training, the sensitivity of the granularity adjustment w.r.t. its input parameters.
- **Real data applicability**: Suitable for application with real-world portfolio data.

---

## Limitations and Potential Pitfalls
We remark the following limitations of the current implementation:

- Note that the current implementation is limited to portfolios between 10 and 100 obligors
- Only ELGDs of either 0.1 or 0.45 are trained
- The creation of Monte-Carlo scenarios is computationally very expensive

---

## Quick Start Guide

1. **Clone the repository**:
   ```bash
   git clone https://github.com/juliansester/DL_Concentration_Risk.git
   
2. **Modify Input:**
  Update MDB portfolios.xlsx as necessary.
3. **Train the Neural Network:**
    Run Compute_GA_approx_MtM.ipynb for Mark-to-Market.
    Run Compute_GA_approx_actuarial.ipynb for Actuarial.
4. **Evaluate Results:**

    Run Portfolio_Evaluation.ipynb for portfolio evaluation
