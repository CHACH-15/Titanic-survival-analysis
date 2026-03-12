🚢 Titanic Survival Analysis

A machine learning project predicting passenger survival on the Titanic using Python. Covers the full data science pipeline — cleaning, EDA, feature engineering, and model comparison across three classifiers.

📁 Repository Structure
titanic-survival-analysis/
├── TitanicPythonScript.ipynb   # Full analysis notebook
├── data/
│   ├── train.csv               # Training set (891 passengers)
│   └── test.csv                # Test set (418 passengers)
├── Titanic_Report.html         # Visual report with all charts
└── README.md

📌 Project Overview
DatasetKaggle Titanic CompetitionTaskBinary classification — survived (1) or not (0)Training set891 passengersTest set418 passengersBest modelDecision Tree (~98% train accuracy)

🔍 Notebook — Steps
1. Data Loading
Imports train.csv and test.csv into pandas DataFrames.
2. Data Cleaning
IssueSolutionCabin — 78% missingDropped entirelyAge — missing valuesImputed with mean per Pclass × Sex groupFare — 1 missingImputed with column meanEmbarked — 2 missingImputed with mode ("S")
3. Feature Engineering

Sex encoded: male→0, female→1
Embarked encoded: S→0, C→1, Q→2
Dropped: PassengerId, Name, Ticket
Features used: Pclass, Sex, Age, Fare, Embarked

4. Exploratory Analysis

Linear regression plots: Pclass vs Survival, Age vs Survival
Survival count by Sex → women survived at 3.7× the male rate
Survival count by Age group → children (0–10) had best odds
Survival count by Pclass → 1st class ~63% survival, 3rd class ~24%

5. Machine Learning Models
ModelTrue NegTrue PosErrorsTrain AccDecision Tree54632718~98% ✅KNN (k=7)522247122~86%SVM (RBF)525214152~83%

📊 Key Findings

Gender is the strongest predictor — 74% of women survived vs 19% of men
Class is the second most predictive — wealth correlated directly with lifeboat access
Children under 10 are the only age group where survivors outnumber casualties
Decision Tree best captures the non-linear patterns in this dataset
SVM had the highest false negative rate — missed 128 actual survivors



📈 Future Improvements

Add cross-validation to get realistic test accuracy
Include SibSp and Parch (family size) as features
Test ensemble methods: Random Forest, Gradient Boosting
Tune Decision Tree depth to reduce overfitting


👤 Author
Chahd
📧moussaouichahd636@gmail.com
🔗https://www.linkedin.com/in/chahd-moussaoui-5501302b6/

📄 Report
A full visual report with all charts is available in Titanic_Report.html — open it in any browser.
