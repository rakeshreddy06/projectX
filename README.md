

## TEAM NAME
ILYA

## TEAM
- Rakesh Reddy - A20525389   (Worked on models output and test file, file structure, took care of readme format and content, project delivery)
- Geeta Hade - A20580824  (done initial math and research on how to build models, took care of readme content)
- Nishant Khandhar - A20581012 (heavily invested time on building code for the Kfold (we faced an issue in it so he took care of it), visualizations )
- Amogh Vastrad - A20588808  (he overlooked and researched the model performance and performed coding for notebook file)

## Project Overview

In this project, we have implemented generic k-fold cross-validation and bootstrapping methods for model selection, which test how well a model is likely to perform on new data. We have also included the Akaike Information Criterion (AIC) to compare models. This model evaluates the performance of regression models and compares it with the AIC.


#### Prerequisites
- Install Python and required libraries: `numpy`, `matplotlib`, `sklearn`.
- Open your terminal or command prompt.
- Navigate to your project folder where the `requirements.txt` file is located.
- Run the following command to install all the libraries listed in `requirements.txt`:


```bash
pip install -r requirements.txt
```
- python version >=3.9



## How to run the code

### Using a Notebook File


#### Steps to Execute
1. Open the terminal at the project folder.
2. Run the command: `jupyter notebook Project2.ipynb`
3. Run all cells sequentially.
4. View the model evaluation outputs (e.g., MSE scores, AIC values) and plots for insights into model performance and residuals.
5. It contains visualizations.

![alt text](image-1.png)

![alt text](image-2.png)

### Using Python Class



#### Steps to Execute
1. Go to the `src` folder.
2. Execute the command: `python .\pythonModelTest.py`

![alt text](image.png)

## Outputs

1. **Cross-Validation:**
    - MSE Scores: [0.2473, 0.2475, 0.2448, 0.2401, 0.2326]
    - Average MSE: 0.2425

2. **Bootstrapping:**
    - MSE Scores (first 5): [0.2408, 0.2316, 0.2475, 0.2507, 0.2412]
    - Average MSE: 0.2397

3. **AIC:**
    - Value: -6247.93

4. **Visualizations:**
    - Residual distribution plot.
    - Error comparison across methods.
    - Bootstrapping confidence intervals.

## Difference Between Bootstrapping and K-Fold Cross-Validation

### Bootstrapping
Bootstrapping is a powerful resampling method where we repeatedly draw samples from our dataset with replacement. Each sample is used to train the model, and its performance is evaluated on the remaining data. By repeating this process many times (e.g., 150 iterations), we can average the results to get a reliable estimate of the model's performance.

### K-Fold Cross-Validation
K-Fold Cross-Validation is a technique where we split the dataset into `k` equal-sized folds. The model is trained on `k-1` folds and tested on the remaining fold. This process is repeated `k` times, ensuring each fold is used once as the test set. By averaging the results, we can estimate the model's performance more accurately.



##



## Key Questions and Answers

1. **Do Cross-Validation and Bootstrapping agree with AIC?**
    - Yes, in our project, we found that all three methods generally agree. For instance, both cross-validation and bootstrapping show lower MSE scores for the chosen model. The AIC value of -6247.93 supports this by indicating a good model fit, aligning well with the performance metrics from cross-validation and bootstrapping.

2. **In what cases might these methods fail?**
    - **Cross-Validation:** May not perform well with very small datasets where the training data in each fold is insufficient to build a reliable model.
    - **Bootstrapping:** Assumes that the data points are independently and identically distributed (i.i.d.); it may not be suitable for datasets with dependencies, such as time series data.
    - **AIC:** Assumes that the residuals of the model are normally distributed; it may provide misleading results for models with non-linear relationships or non-normal residuals.

3. **How can we address these challenges?**
    - For imbalanced datasets, consider using stratified k-fold cross-validation to ensure each fold has a representative distribution of the target variable.
    - For datasets with dependencies, such as time series data, use block bootstrapping to maintain the inherent structure and relationships within the data.
    - To improve the reliability of AIC, especially for small sample sizes, use corrected versions like AICc (Akaike Information Criterion corrected).

4. **What parameters can you customize in our project?**
    - **Cross-Validation:** You can set the number of folds (`k`), with a default value of 5.
    - **Bootstrapping:** You can specify the number of iterations (`num_iterations`), which defaults to 100, and set a seed for reproducibility.
    - **Regression Models:** You can adjust the regularization parameter (`alpha`) for Ridge regression, with a default value of 1.0.

## Additional Features
- Synthetic data generator
- Synthetic data generator for flexible testing.
- Residual analysis and visualization tools for insights.
- Extendable framework for adding new model selectors.

## Compatibility
- Tested on Windows
- Requires `numpy`, `matplotlib`, `Jupyter`, `sklearn`

## More data
- if you had time check data folder for various plot and results
