# FFFL_Aysmptotic_NeuralNet

### Citation
Please cite the following paper if you use this code in your work:

Fabozzi, Frank J., Fallahgoul, Hasan A., Fallahgoul, Hasan A., Franstianto, Vincentius, and Loeper, Gregoire. "Asymptotic Properties of ReLU FFN Sieve Estimators," *Studies in Nonlinear Dynamics & Econometrics*, forthcoming.  
Available at SSRN: [https://ssrn.com/abstract=3499324](https://ssrn.com/abstract=3499324) or [http://dx.doi.org/10.2139/ssrn.3499324](http://dx.doi.org/10.2139/ssrn.3499324).

### Library Versions:
- Python 3.12.4
- TensorFlow 2.16.1
- NumPy 1.26.4
- Pandas 2.2.1
- SciPy 1.13.1
- Matplotlib 3.8.4

### Overview

This repository contains code for replicating the results presented in the paper. Below is a guide to help you understand the structure of the code and the key variables involved in the simulations.

### Key Variables and Parameters

1. Mean Function (`f0`) and Sample Size (`nSamples`):
   - The variable `thef0Name` represents the name and notation of the mean function `f0`. 
   - The variable `part` specifies the origin of the function:
     - `part == "part 2"` refers to functions from Shen et al.
     - `part == "part 1"` refers to functions created for this paper.
   - The `iterationRange` variable determines the number of samples (`nSamples`) to be used in the simulations.

2. Activation Function:
   - The `activationChoice` variable specifies the activation function used by the neural networks. 
   - For example, if `activationChoice == 2`, the sigmoid activation function is used, and the depth of the network (`L`) is set to 1.

### Code Structure and Workflow

The code is designed to validate the asymptotic normality of the predicted values by generating Q-Q plots against a normal distribution. Below is an outline of the workflow:

1. Preparation:
   - Set up the required input variables, including `thef0Name`, `iterationRange`, and others necessary for training the neural networks.

2. Data Generation and Training Loop:
   - The loop starting at line 98 handles the following:
     - Generates data for each sample size within the range `[2000, 5000, 20000, 50000, 200000]`.
     - Trains the neural networks.
     - Calculates normality statistical test values.
     - Plots the curves of `f0` and the predicted values.
     - Generates Q-Q plots for assessing the asymptotic normality of the predicted values.

3. Detailed Loop Breakdown:
   - **Part 1:** Data generation, neural network creation, training, prediction, and calculation of `rho_square` values.
   - **Part 2:** Conducts the Kolmogorov-Smirnov, Anderson-Darling, and Shapiro-Wilk tests on the predicted values to assess normality.
   - **Part 3:** Plots the convergence and consistency of `f0` and the predicted values for each sample size. Additionally, generates Q-Q plots of the predicted values against the normal distribution to demonstrate asymptotic normality.

