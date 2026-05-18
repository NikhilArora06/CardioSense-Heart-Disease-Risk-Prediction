# CardioSense — Heart Disease Risk Prediction

I built this project to see how effectively standard machine learning classification algorithms can predict heart disease based on common patient clinical data. 

When it comes to healthcare, a false positive means unnecessary stress and testing, but a false negative could be fatal. Because of that, I designed this pipeline with a heavy focus on Precision and cross-validation to make sure the predictions are as reliable as possible.

## The Game Plan and Results

I trained and tested three different models on the classic UCI Cleveland dataset. Since predicting who actually has heart disease accurately was the priority, Logistic Regression won by a landslide after hyperparameter tuning.

* Logistic Regression (Tuned): 88.52% Top Precision Score
* Random Forest: 83.61% Top Precision Score
* K-Nearest Neighbors (KNN): 68.85% Top Precision Score

### Going Deeper with Cross-Validation
A single train-test split can be lucky, so I ran a 5-fold cross-validation on the Logistic Regression model (C=0.2043, solver="liblinear") to see how it handles unseen data. Here are the average scores:

* Accuracy: 84.47% (Solid overall performance)
* Precision: 82.08% (Keeps false alarms low)
* Recall: 92.12% (Crucial: This means it catches over 92% of actual heart disease cases)
* F1-Score: 86.73% (Great balance between precision and recall)

## The Tech I Used
* Language: Python
* Data Wrangling: Pandas and NumPy
* Machine Learning: Scikit-Learn
* Charts and Plots: Matplotlib and Seaborn
* Workspace: Jupyter Notebook

## What is in the Dataset?
The data comes from the UCI Machine Learning Repository and contains 14 total columns: 13 clinical features (inputs) used to predict 1 target variable (the output).
### The 13 Features:
1. **Age:** Patient age in years
2. **Sex:** 1 = male, 0 = female
3. **Chest Pain Type (cp):** Type of chest pain experienced (coded 0-3)
4. **Resting Blood Pressure (trestbps):** Blood pressure in mm Hg upon admission
5. **Serum Cholesterol (chol):** Cholesterol measurement in mg/dl
6. **Fasting Blood Sugar (fbs):** 1 = > 120 mg/dl, 0 = lower
7. **Resting Electrocardiographic Results (restecg):** ECG values (coded 0-2)
8. **Maximum Heart Rate Achieved (thalach):** Highest heart rate recorded during testing
9. **Exercise-Induced Angina (exang):** 1 = yes, 0 = no
10. **Oldpeak:** ST depression induced by exercise relative to rest
11. **Slope:** The slope of the peak exercise ST segment
12. **Ca:** Number of major vessels colored by fluoroscopy (0-3)
13. **Thal:** Thallium stress test results

### The Target Variable:
* **Target:** 1 = heart disease present, 0 = healthy (no heart disease


## Installation & Setup

### Clone repository

```bash
git clone https://github.com/NikhilArora06/CardioSense-Heart-Disease-Risk-Prediction
cd CardioSense
```

### Create virtual environment

```bash
python -m venv .venv
```

### Activate environment

**Windows**

```bash
.\.venv\Scripts\activate
```

**Mac/Linux**

```bash
source .venv/bin/activate
```

### Install dependencies

```bash
pip install -e .
```

This command:

- installs dependencies from `requirements.txt`
- installs CardioSense in editable mode
- creates package metadata (`CardioSense.egg-info`)

---

## Repository Structure

CardioSense/
│
├── .gitignore
├── README.md
├── requirements.txt
├── setup.py
├── cardiosense_evaluation.ipynb
├── cleveland_heart_disease.csv
