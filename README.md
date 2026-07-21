# Binary Random Forest Contact Detection

## Overview

This project implements a **Binary Random Forest classifier** for contact detection using resistance measurements from an MXene-based smart composite sensor.

The model classifies each measurement as:

- **0** → No Contact
- **1** → Contact

Eight resistance channels (`R_1`–`R_8`) are used as the input features.

---

# Dataset

Dataset:

```
matriz_4x4_dataset_unificado_force_class.csv
```

Input features:

```
R_1
R_2
R_3
R_4
R_5
R_6
R_7
R_8
```

Target:

```
Force
```

---

# Workflow

1. Load dataset
2. Select input features
3. Create train/test split
4. Perform hyperparameter tuning using RandomizedSearchCV
5. Train the best Random Forest model
6. Evaluate performance
7. Perform 5-fold cross-validation
8. Compute feature importance
9. Save trained model

---

# Required Libraries

```python
pandas
numpy
scikit-learn
matplotlib
seaborn
joblib
```

Install using:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib
```

---

# Important

The train/test split **must** be written as:

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.25,
    stratify=y,
    random_state=42
)
```

Calling

```python
train_test_split(...)
```

without assigning the outputs will **not** create `X_train`, `X_test`, `y_train`, or `y_test`.

---

# Model

Algorithm:

```
Random Forest Classifier
```

Hyperparameter tuning:

```
RandomizedSearchCV
```

Cross-validation:

```
5-Fold Stratified Cross Validation
```

Evaluation metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC AUC
- Confusion Matrix
- Feature Importance

---

# Best Results

| Metric | Score |
|--------|------:|
| Accuracy | 94.10% |
| Precision | 90.41% |
| Recall | 85.87% |
| F1 Score | 88.08% |
| ROC AUC | 97.68% |

---

# Cross Validation

Mean F1 Score:

```
0.8790
```

Standard Deviation:

```
0.0011
```

---

# Feature Importance

1. R7
2. R5
3. R3
4. R1
5. R2
6. R8
7. R6
8. R4

---

# Saved Model

The trained model is saved as:

```
binary_random_forest.pkl
```

Load using:

```python
import joblib

model = joblib.load("binary_random_forest.pkl")
```

---

# Author

**Caden D'Souza**

Summer Research Internship

MXene-Based Smart Composite Contact Detection
