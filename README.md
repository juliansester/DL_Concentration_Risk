
# Code for "Measuring Name Concentrations through Deep Learning"

## Eva Lütkebohmert, Julian Sester

# Abstract
We propose a new deep learning approach for the quantification of name concentration risk in loan portfolios. Our approach is tailored for small portfolios and allows for both an actuarial as well as a mark-to-market definition of loss. The training of our neural network relies on Monte Carlo simulations with importance sampling which we explicitly formulate for the CreditRisk+ and the ratings-based CreditMetrics model. Numerical results based on simulated as well as real data demonstrate the accuracy of our new approach and its superior performance compared to existing analytical methods for assessing name concentration risk in small and concentrated portfolios. 

# Preprint
[Available on arxiv](https://arxiv.org/abs/2403.16525)

## Table of Contents
The repo contains the following notebooks and python files.

- ### Creation of Scenarios
	Notebooks to create Monte-Carlo simulations of scenarios.

	-[Create_Scenarios_MtM.ipynb](Create_Scenarios_MtM.ipynb) (for the Mark-to-Market case)
	-[Create_Scenarios_actuarial.ipynb](Create_Scenarios_actuarial.ipynb) (for the actuarial case)
- ### Training of Neural Networks
	Notebooks to train the neural networks.

	-[Compute_GA_approx_MtM.ipynb](Compute_GA_approx_MtM.ipynb) (for the Mark-to-Market case)
	-[Compute_GA_approx_actuarial.ipynb](Compute_GA_approx_actuarial.ipynb) (for the actuarial case)

	The python code is contained here: 

	-[MtM_training.py](MtM_training.py) (for the Mark-to-Market case)
	-[actuarial_training.py](actuarial_training.py) (for the actuarial case)
- ### Definition of necessary auxiliary functions
	-[IS_misc_functions.py](IS_misc_functions.py)
	-[misc_functions.py](misc_functions.py)
- ### Sensitivity Analysis
	-[Sensitivities_mtm.ipynb](Sensitivities_mtm.ipynb) (for the Mark-to-Market case)
	-[Sensitivities_actuarial.ipynb](Sensitivities_actuarial.ipynb) (for the actuarial case)
- ### Evaluation with real MDB portfolios
	-[Portfolio_Evaluation.ipynb](Portfolio_Evaluation.ipynb) (notebook)
	-[MDB portfolios.xlsx](MDB portfolios.xlsx) (excel file with the data on the MDB portfolios)
	-[transition_matrix_RC.csv](transition_matrix_RC.csv), [transition_matrix_SP.csv](transition_matrix_SP.csv) (the used transition matrices)
	
[probs.txt](probs.txt) (the probabilities that can be attained according to the S&P matrix)
	
- ### Misc
	[scaler_actuarial.gz](scaler_actuarial.gz) (scaler for the actuarial neural network)

	[scaler_mtm.gz](scaler_mtm.gz) (scaler for the MtM neural network)



## Features
- The code allows to train neural networks for the actuarial case (Credit Risk+) and the mark-to market case (Credit Metrics) to compute granularity adjustments given credit portfolios characteristics as input.
- Upon training, one can perform a sensitivity analysis.
- The approach is applicable to real data.

## Limitations of the Approach and Potential Pitfalls
We remark the following limitations of the current implementation:
- Note that the current implementation is limited to portfolios between 10 and 100 obligors
- Only ELGDs of either 0.1 or 0.45 are trained
- The creation of Monte-Carlo scenarios is computationally very expensive

### Step-by-Step Guide for application to portfolio data
```bash
# Clone the repository
git clone https://github.com/juliansester/DL_Concentration_Risk.git

# Adjust the excel file 
Change MDB portfolios.xlsx according to the changed input

# Train the neural network
Run Compute_GA_approx_MtM.ipynb and Compute_GA_approx_actuarial.ipynb

# Evaluate the results
Run Portfolio_Evaluation.ipynb



