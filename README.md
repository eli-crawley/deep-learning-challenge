# Neural Network Model Report: AlphabetSoupCharity Optimization

## Overview of the Analysis
The goal of this analysis is to create a neural network model that predicts whether an organization will be successful in securing funding from Alphabet Soup, a philanthropic foundation. This classification task uses historical application data and aims to help streamline the charity’s grant application review process by identifying promising applications early.

## Results
###  Data Preprocessing
* Target Variable: 
  *  IS_SUCCESSFUL: A binary value indicating whether the application was funded (1) or not (0).
*  Features (Input Variables):
    * Numerical variables like APPLICATION_TYPE, CLASSIFICATION, USE_CASE, ORGANIZATION, INCOME_AMT, etc. (after encoding).
    * Encoded categorical features resulting from one-hot encoding.
* Variables Removed:
    * EIN: Employer Identification Number – a unique identifier not useful for training.
    * NAME: Organization name – irrelevant and non-numeric.
    * Any columns with high cardinality or no predictive value.
### Compiling, Training, and Evaluating the Model
* Model Architecture:

  | Layer          | Neurons | Activation |
  | -------------- | ------- | ---------- |
  | Hidden Layer 1 | 80      | ReLU       |
  | Hidden Layer 2 | 30      | ReLU       |
  | Output Layer   | 1       | Sigmoid    |
* Justification:
    * The number of neurons was based on common heuristics (average of input/output size).
    * ReLU used for hidden layers for faster convergence.
    * Sigmoid used in output to predict binary outcome. 
* Model Performance:
    * Accuracy achieved: ~72.5%
    * Target performance: 75%+ (so the model slightly underperformed)
* Steps Taken to Improve Performance:
    * Hyperparameter tuning (changing number of neurons and layers).
    * Trying different batch sizes and epochs.
    * Testing additional hidden layers and dropout layers (not shown to improve significantly).

## Summary
* The neural network achieved ~72.5% accuracy, which is close but below the target of 75%.
* The model structure is sound, and performance was improved incrementally through tuning, though not to the desired threshold.

## Recommendations
To further improve performance, it is recommended to:

Try a different model such as:
* Random Forest: It often handles tabular data with mixed feature types better.
* XGBoost: Known for strong performance on structured data.
* Ensemble Learning: Combine neural networks with tree-based models for improved results.

These models offer better interpretability and may capture non-linear relationships more effectively in this dataset than a basic neural network.