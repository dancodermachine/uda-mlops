# Model Fairness Assessment
**Model fairness assessment** evaluates whether a ML model produces systematically biased or prejudiced outcomes against certain groups.

ML models learn patterns from training data, including historical human biases. As a result, biased training data can lead to models that reproduce or reinforce those biases.

Even when sensitive attributes are removed, models may still learn discriminatory patterns through **proxy features**—variables that correlate with sensitive attributes.

For example, features such as zip code, income, or university attended may indirectly reveal demographic information. Therefore, removing sensitive attributes alone does not guarantee fairness.

## 1. Measuring Fairness
Fairness assessment involves evaluating model performance across different demographic subgroups rather than relying solely on aggregated metrics. Two key fairness metrics are:
* **Demographic Parity Difference (DPD)**: It measures differences in positive prediction rates across demographic groups. For example, in a loan approval model, it evaluates whether different groups receive favorable predictions at similar rates. A large DPD indicates a significant disparity in positive outcomes between groups.
* **Equalized Odds Difference (EOD)**: It measures differences in true positive rates and false positive rates across demographic groups. A larger EOD indicates greater disparities in error rates between groups. It evaluates whether a model makes errors at similar rates for different groups, including:
    - **False Positives**: Incorrectly predicting a positive outcome.
    - **False Negatives**: Incorrectly predicting a negative outcome.
    
## 2. Bias Mitigation
Bias mitigation involves applying techniques to reduce unfair outcomes at different stages of the machine learning lifecycle.

### 2.1 Pre-processing
**Pre-processing** applies bias mitigation techniques to the training data before model training begins. Common approaches include:
* **Resampling**: Adjusting the representation of underrepresented groups in the training dataset.
* **Reweighting**: Assigning different weights to training examples to improve group balance.
* **Correlation Removal**: Reducing statistical relationships between sensitive attributes and other features.

### 2.2 In-processing
**In-processing** modifies the model's learning process to incorporate fairness considerations during training. This can involve:
* **Sample Reweighting**: Giving greater importance to examples from underrepresented groups during training.
* **Fairness Constraints**: Adding fairness requirements to the model's objective function so it optimizes for both predictive performance and equity.

### 2.3 Post-processing
**Post-processing** adjusts a trained model's predictions to reduce disparities between demographic groups.

A common technique involves applying different decision thresholds to different subgroups to equalize outcomes.

This approach does not require retraining the underlying model.

## 3. Automated Fairness Gate
A **fairness gate** is an automated checkpoint in a deployment pipeline that verifies whether a model meets predefined fairness requirements before being released.

For example, a pipeline might enforce a maximum acceptable **Equalized Odds Difference (EOD)**.

If a model exceeds the specified threshold, deployment is automatically blocked, preventing models that fail fairness requirements from reaching production.

Tools:
* Fairlearn
* IBM AI Fairness 360