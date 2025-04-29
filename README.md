# Assignment 3 – EM Algorithm for Mixture Models
 
**Subject**: MAST30027  

## Overview

This project implements the Expectation-Maximization (EM) algorithm to estimate parameters of a 3-component mixture model based on negative binomial distributions. The task is completed in two parts:

1. **Part 1**: EM on Unlabeled Data (`X`)
2. **Part 2**: EM on Partially Labeled Data (`X` and `X.more`)

---

## Part 1: EM on Original Dataset

The file `assignment3_2024_prob1.txt` contains a sample from a mixture of three negative binomial distributions.

### Approach

- Load and visualize the data.
- Implement the EM algorithm in R to estimate:
  - Mixture weights (π₁, π₂, π₃)
  - Negative binomial probabilities (p₁, p₂, p₃)
- Use two sets of starting values.
- Select the result with the highest final log-likelihood.
- Plot log-likelihood to verify convergence.

### Final Estimates

**Best Run** (after accounting for label switching):

- Mixture weights:  
  `π = (0.22, 0.50, 0.28)`
- Negative binomial probabilities:  
  `p = (0.14, 0.56, 0.26)`

---

## Part 2: EM with Additional Labeled Data

An extra dataset `assignment3_2024_prob2.txt` (`X.more`) is introduced, known to come from **component 1** of the mixture.

### Approach

- Incorporate `X.more` into the EM algorithm.
- Adjust the M-step for component 1 using the new data.
- Run EM with two different sets of initial values.
- Choose the result with the highest final log-likelihood.

### Final Estimates

**Best Run**:

- Mixture weights:  
  `π = (0.26, 0.25, 0.48)`
- Negative binomial probabilities:  
  `p = (0.28, 0.14, 0.56)`

---

## Code Structure

Key functions in the R code:

- `mixture.EM()` – Main EM routine
- `EM.iter()` – One iteration of EM (E-step + M-step)
- `compute.prob.x.z()` – Compute joint probability matrix
- `compute.log.lik()` – Calculate the log-likelihood

---

## Outputs

- Histograms of datasets
- Log-likelihood plots showing convergence
- Final parameter estimates for each EM run
- PNG plots: `1.png` to `5.png`

---

## Files Included

