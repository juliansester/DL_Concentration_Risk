
# Code for "Measuring Name Concentrations through Deep Learning"

## Eva Lütkebohmert, Julian Sester

# Abstract
We propose a new deep learning approach for the quantification of name concentration risk in loan portfolios. Our approach is tailored for small portfolios and allows for both an actuarial as well as a mark-to-market definition of loss. The training of our neural network relies on Monte Carlo simulations with importance sampling which we explicitly formulate for the CreditRisk+ and the ratings-based CreditMetrics model. Numerical results based on simulated as well as real data demonstrate the accuracy of our new approach and its superior performance compared to existing analytical methods for assessing name concentration risk in small and concentrated portfolios. 

# Preprint
[Available here](https://arxiv.org/abs/2403.16525)

## Table of Contents
- [Description](#description)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)



## Features
- Feature 1
- Feature 2
- Feature 3
*(List main features or functionality of the project.)*

### Step-by-Step Guide
```bash
# Clone the repository
git clone https://github.com/username/repo-name.git

# Navigate to the project directory






# Limitations and Potential Pitfalls
We remark the following limitations of the current implementation:
- Note that the current implementation is limited to portfolios between 10 and 100 obligors
- Only ELGDs of either 0.1 or 0.45 are trained
- The creation of Monte-Carlo scenarios is computationally very expensive
