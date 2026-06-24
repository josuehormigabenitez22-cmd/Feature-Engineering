### Feature Discovery

#### Objective

Before creating new features or performing Feature Engineering, it is essential to identify which variables already contain useful information for the model.

This module presents three classic approaches for evaluating feature relevance:

* Correlation Analysis
* Mutual Information
* Tree-Based Feature Importance

---

### 1. Correlation Analysis

Correlation measures the linear relationship between variables.

#### Advantages

* Easy to interpret
* Very fast to compute
* Detects redundancy between variables

#### Limitations

* Only captures linear relationships
* May overlook complex relationships

#### Typical Use Cases

* Remove highly correlated variables
* Identify variables related to the target

---

### 2. Mutual Information (MI)

Mutual Information measures how much information a variable provides about the target.

Unlike correlation, it:

* Detects both linear and non-linear relationships
* Works for both classification and regression tasks
* Makes no assumptions about data distribution

#### Interpretation

* **MI = 0** → the feature provides no information
* **High MI** → the feature is relevant

---

### 3. Tree-Based Feature Importance

Tree-based models (Random Forest, XGBoost, LightGBM) automatically compute the importance of each variable.

#### Advantages

* Capture complex relationships
* Account for interactions between variables
* Robust to feature scaling

#### Limitations

* May favor variables with many unique values
* Importance does not imply causality

---

### Recommended Workflow

1. Review correlations
2. Compute Mutual Information
3. Train a Random Forest model
4. Compare feature rankings
5. Remove irrelevant variables
6. Perform Feature Engineering only on promising variables

---

### Conclusion

Feature Discovery helps reduce noise, simplify models, and accelerate the feature engineering process.

Before creating new features, it is advisable to understand which existing variables already contain sufficient predictive signal.
