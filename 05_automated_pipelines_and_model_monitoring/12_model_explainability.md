# Model Explainability
**Model explainability** is the practice of understanding and interpreting the predictions and decisions made by machine learning models. 

Complex models, such as deep neural networks, often behave as **black-box models**, meaning their internal decision-making logic is difficult for humans to interpret.

Explainability helps make these models more transparent, enabling developers to debug unexpected behavior and justify predictions to users, auditors, and regulators.

## 1. Two Levels of Explainability
1. **Local Explainability**: It focuses on understanding the factors that influenced a single, specific prediction. For example, if a model rejects a loan application, a local explanation can identify the features that contributed to the decision, such as a recent missed payment. This is useful for investigating unexpected predictions and explaining individual outcomes to users.
2. **Global explainability**: It examines a model's overall decision-making patterns across multiple predictions. It identifies which features generally have the greatest influence on the model's outputs and helps detect potential issues. For example, if a model assigns unexpectedly high importance to a feature such as zip code, this may indicate potential bias.

Explainability can also complement **drift monitoring**. While drift detection identifies changes in data or model behavior, explainability analysis helps determine which features are contributing to those changes.

## 2. Understanding SHAP and LIME
SHAP and LIME are two common techniques for explaining predictions made by complex machine learning models.

### 2.1 SHAP (SHapley Additive exPlanations)
**SHAP** is a game-theory-based technique that assigns an importance value to each feature, representing its contribution to a specific prediction. It supports two levels of explanation:
* **Local Explanation**: Quantifies how individual features contribute to a particular prediction.
* **Global Explanation**: Aggregates feature contributions across a dataset to identify overall feature importance.

SHAP provides mathematically grounded and consistent explanations, making it particularly useful for:
* Formal model audits.
* Bias detection.
* Situations requiring defensible and interpretable predictions.

### 2.2 LIME (Local Interpretable Model-agnostic Explanations)
**LIME** explains individual predictions by approximating a complex model's behavior with a simpler, interpretable model, such as linear regression, in the local neighborhood of a prediction.

It is **model-agnostic**, meaning it can be applied to different types of machine learning models without requiring access to their internal structure.

**LIME is generally faster than SHAP** and is particularly useful for:
* Real-time explanations where speed is important.
* Rapid debugging of individual predictions.
* Exploratory analysis of model behavior.