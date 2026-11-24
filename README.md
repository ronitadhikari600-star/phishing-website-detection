# Phishing Website Detection System

A machine learning project that predicts whether a website is **Potentially Phishing** or **Likely Legitimate**.

## Dataset
`phishing.csv` has 11,054 website records with 30 features. The target column `class` is -1 for phishing and 1 for legitimate. After removing duplicates, 5,849 records are used.

## Project Steps
1. Load and understand the dataset
2. Preprocess the data
3. Exploratory data analysis (EDA)
4. Train/test split (80/20, stratified)
5. Train three models: Logistic Regression, Decision Tree, Random Forest
6. Evaluate and compare the models
7. 5-fold cross-validation
8. Hyperparameter tuning with GridSearchCV
9. Select the best model and test it
10. Classify new websites from a URL or from 30 feature values
11. Save the model with joblib

## Results
The selected model is a tuned Random Forest (`max_depth=20`, `n_estimators=100`).

| Metric (test set) | Score |
|---|---|
| Accuracy | 0.9436 |
| Precision (phishing) | 0.9513 |
| Recall (phishing) | 0.9387 |
| F1-score | 0.9450 |

A separate URL-only model (10 URL-based features) reaches about 0.88 accuracy, so it is less reliable.

## How to Run
1. Install the libraries:
   ```
   pip install numpy pandas matplotlib seaborn scikit-learn joblib jupyter
   ```
2. Keep `phishing.csv` and the notebook in the same folder.
3. Open `phishing_project_full (1).ipynb` and run all cells.
4. In Step 10, remove the `#` before `classify_new_website()` to enter your own URL or feature values.

## Example
```
Enter website URL: https://www.google.com
Prediction: Likely Legitimate
```

## Output Folder
Saved models, plots, the comparison table and the cleaned data are written to the `output` folder.

## Author
Ronit Adhikari
