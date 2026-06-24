# Baseline Model

## Introduction

Before creating new features, applying transformations, or experimenting with different machine learning techniques, it is essential to establish a baseline.

A baseline model provides a reference point against which all future improvements can be measured.

Without a baseline, it is impossible to determine whether a newly created feature genuinely improves model performance or simply adds complexity.

For this reason, building a baseline model is considered a fundamental step in any machine learning project.

---

# What is a Baseline Model?

A baseline model is the initial version of a machine learning model trained using the available data with minimal modifications.

Its purpose is not to achieve the highest possible performance.

Instead, its purpose is to establish a benchmark that future experiments must surpass.

The baseline represents the current level of performance before any feature engineering or optimization is applied.

---

# Why Baselines Matter

Feature engineering is an experimental process.

Every new feature represents a hypothesis about the data.

Without a baseline, there is no objective way to evaluate whether a hypothesis is correct.

A baseline allows us to:

* Measure improvements.
* Detect performance degradation.
* Compare experiments fairly.
* Avoid unnecessary complexity.
* Quantify the impact of new features.

---

# Baselines and Feature Engineering

The primary objective of feature engineering is to improve predictive performance.

To determine whether a feature is useful, we compare model performance before and after introducing the feature.

The process follows a simple cycle:

```text
Build Baseline
        ↓
Create Feature
        ↓
Train New Model
        ↓
Compare Results
        ↓
Keep or Remove Feature
```

Only features that provide measurable improvements should be retained.

---

# Characteristics of a Good Baseline

A good baseline should be:

## Simple

The model should be easy to train and interpret.

The purpose is to create a reference point, not a highly optimized solution.

---

## Reproducible

The experiment should be repeatable.

Random seeds, validation procedures, and preprocessing steps should be documented.

---

## Stable

Performance should remain relatively consistent across different validation folds or data splits.

---

## Relevant

The baseline should use the same evaluation metric that will be used throughout the project.

---

# Building a Baseline Model

A typical baseline construction process consists of the following steps.

## Step 1: Define the Target

Clearly identify the variable to be predicted.

Examples:

* House price
* Customer churn
* Credit default
* Product demand

---

## Step 2: Select Initial Features

Use the original dataset with minimal transformations.

Avoid extensive feature engineering at this stage.

The objective is to measure the predictive power of the raw data.

---

## Step 3: Select a Model

Choose a reasonable model appropriate for the problem.

Examples:

### Regression

* Linear Regression
* Random Forest Regressor
* Gradient Boosting Regressor

### Classification

* Logistic Regression
* Random Forest Classifier
* Gradient Boosting Classifier

The exact algorithm is often less important than having a consistent reference point.

---

## Step 4: Define a Validation Strategy

The validation procedure determines how performance will be measured.

Common approaches include:

### Train-Test Split

Simple and fast.

Suitable for initial experiments.

---

### Cross Validation

Provides more reliable estimates.

Reduces dependence on a single data split.

Often preferred in feature engineering workflows.

---

### Time Series Validation

Used when observations have temporal order.

Prevents future information from leaking into training data.

---

## Step 5: Measure Performance

Evaluate the model using an appropriate metric.

This score becomes the baseline.

---

# Evaluation Metrics

The evaluation metric depends on the problem type.

---

## Regression Metrics

### Mean Absolute Error (MAE)

Measures the average absolute prediction error.

Advantages:

* Easy to interpret.
* Robust to outliers.

---

### Mean Squared Error (MSE)

Measures average squared error.

Advantages:

* Penalizes large mistakes more heavily.

---

### Root Mean Squared Error (RMSE)

Square root of MSE.

Advantages:

* Expressed in the original target units.

---

### R² Score

Measures how much target variance is explained by the model.

Range:

* 1 = perfect prediction
* 0 = no improvement over the mean prediction

---

## Classification Metrics

### Accuracy

Percentage of correctly classified observations.

---

### Precision

Measures prediction quality among positive predictions.

---

### Recall

Measures how many true positives were identified.

---

### F1 Score

Balances precision and recall.

---

### ROC-AUC

Measures ranking quality across classification thresholds.

---

# Comparing Experiments

Every feature engineering experiment should be compared against the same baseline.

Example:

| Experiment | MAE   |
| ---------- | ----- |
| Baseline   | 10.42 |
| Feature A  | 9.87  |
| Feature B  | 10.65 |
| Feature C  | 9.31  |

Interpretation:

* Feature A improves performance.
* Feature B hurts performance.
* Feature C provides the largest improvement.

This process allows objective decision-making.

---

# Common Mistakes

## No Baseline

Without a baseline, performance improvements cannot be measured.

---

## Changing Multiple Things at Once

If several features are added simultaneously, it becomes difficult to identify which feature caused the improvement.

Whenever possible, test features incrementally.

---

## Using Different Validation Strategies

Changing the validation procedure between experiments invalidates comparisons.

The validation methodology should remain consistent.

---

## Data Leakage

Using information unavailable at prediction time can artificially inflate performance.

A feature that improves performance because of leakage is not useful in production.

---

# Feature Engineering as a Scientific Process

Feature engineering should be approached as a sequence of experiments.

Each feature represents a hypothesis.

For example:

> "This ratio may contain information relevant to the target."

The hypothesis is tested by:

1. Creating the feature.
2. Retraining the model.
3. Comparing against the baseline.

If performance improves, the hypothesis gains support.

If performance does not improve, the feature should be reconsidered or discarded.

---

# Practical Workflow

A typical feature engineering workflow follows this structure:

```text
Raw Dataset
        ↓
Baseline Model
        ↓
Feature Hypothesis
        ↓
Feature Creation
        ↓
Model Retraining
        ↓
Performance Comparison
        ↓
Feature Selection
```

This cycle is repeated throughout the project.

---

# Key Takeaways

* A baseline model is the reference point for all future experiments.
* Every feature should be evaluated relative to the baseline.
* Improvements must be measured using a consistent validation strategy.
* Feature engineering should be treated as an experimental process.
* The objective is not to create more features, but to create features that improve measurable performance.
* Without a baseline, it is impossible to know whether feature engineering is actually working.
