
# 🚢 Titanic Survival Analysis

🌐 Live Report
👉 

A machine learning project predicting passenger survival on the Titanic using Python. Covers the full data science pipeline — cleaning, EDA, feature engineering, and model comparison across three classifiers.

---

## 📁 Repository Structure

```
titanic-survival-analysis/
├── TitanicPythonScript.ipynb   # Full analysis notebook
├── data/
│   ├── train.csv               # Training set (891 passengers)
│   └── test.csv                # Test set (418 passengers)
├── Titanic_Report.html         # Visual report with all charts
└── README.md
```

---

## 📌 Project Overview

| | |
|---|---|
| **Dataset** | Kaggle Titanic Competition |
| **Task** | Binary classification — survived (1) or not (0) |
| **Training set** | 891 passengers |
| **Test set** | 418 passengers |
| **Best model** | Decision Tree (~98% train accuracy) |

---

## 🔍 Notebook — Steps

### 1. Data Loading
Imports `train.csv` and `test.csv` into pandas DataFrames.

### 2. Data Cleaning
| Issue | Solution |
|---|---|
| `Cabin` — 78% missing | Dropped entirely |
| `Age` — missing values | Imputed with mean per Pclass × Sex group |
| `Fare` — 1 missing | Imputed with column mean |
| `Embarked` — 2 missing | Imputed with mode ("S") |

### 3. Feature Engineering
- `Sex` encoded: male→0, female→1
- `Embarked` encoded: S→0, C→1, Q→2
- Dropped: `PassengerId`, `Name`, `Ticket`
- Features used: `Pclass`, `Sex`, `Age`, `Fare`, `Embarked`

### 4. Exploratory Analysis
- Linear regression plots: Pclass vs Survival, Age vs Survival
- Survival count by Sex → women survived at 3.7× the male rate
- Survival count by Age group → children (0–10) had best odds
- Survival count by Pclass → 1st class ~63% survival, 3rd class ~24%

### 5. Machine Learning Models

| Model | True Neg | True Pos | Errors | Train Acc |
|---|---|---|---|---|
| **Decision Tree** | 546 | 327 | 18 | ~98% ✅ |
| **KNN (k=7)** | 522 | 247 | 122 | ~86% |
| **SVM (RBF)** | 525 | 214 | 152 | ~83% |

---

## 📊 Key Findings

- **Gender** is the strongest predictor — 74% of women survived vs 19% of men
- **Class** is the second most predictive — wealth correlated directly with lifeboat access
- **Children under 10** are the only age group where survivors outnumber casualties
- **Decision Tree** best captures the non-linear patterns in this dataset
- **SVM** had the highest false negative rate — missed 128 actual survivors

---

## 🚀 How to Run

```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# Launch notebook
jupyter notebook TitanicPythonScript.ipynb
```

> ⚠️ Update the CSV file paths in the first code cell to your local directory.

---

## 🛠 Tech Stack

| Tool | Purpose |
|---|---|
| Python 3 | Core language |
| Pandas | Data manipulation |
| Matplotlib / Seaborn | Visualizations |
| Scikit-learn | ML models (Decision Tree, SVM, KNN) |
| Jupyter Notebook | Interactive analysis |

---

## 📈 Future Improvements

- Add cross-validation to get realistic test accuracy
- Include `SibSp` and `Parch` (family size) as features
- Test ensemble methods: Random Forest, Gradient Boosting
- Tune Decision Tree depth to reduce overfitting



## 👤 Author

**Chahd**  
📧 moussaouichahd636@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/chahd-moussaoui-5501302b6/)

---

## 📄 Report

A full visual report with all charts is available in [`Titanic_Report.html`](./Titanic_Report.html) — open it in any browser.
