# Task 5: Exploratory Data Analysis – Titanic Dataset

**Objective**  
Perform a comprehensive statistical and visual exploration of the Titanic dataset to uncover patterns, relationships, and actionable insights.

---

## 📁 File Structure
```plaintext
Task5_Exploratory_Data_Analysis/
├── README.md                 # This file (summary + how-to guide)
├── train.csv                 # Raw Titanic training dataset
├── gender_submission.csv     # Sample passenger survival predictions
└── task5.ipynb                # Jupyter Notebook with complete EDA
```

---

## ⚡ How to Run

1. Clone or download this folder into your local machine (or coding workspace).
2. Install the required Python packages:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter lab
   ```
4. Open and run `task5.ipynb` from top to bottom.
5. After completing the analysis, export the final report as **PDF** if needed.

---

## 📑 Deliverables

- **Jupyter Notebook (`task5.ipynb`)**: Includes data loading, cleaning checks, feature engineering, EDA visualizations, and observations.
- **Optional Report**: Export a clean PDF version from the notebook (for sharing or submission).

---

## 📄 Report Content

### 1. Introduction
The Titanic dataset captures passenger information related to the 1912 disaster.  
**Goals**:
- Analyze demographic, ticket, and family-related factors influencing survival.
- Identify patterns based on gender, age, class, and fare.
- Provide recommendations for further predictive modeling.

---

### 2. Data Overview
- **Rows**: 891 passenger records
- **Columns**: 12 features, including:
  - Survived, Pclass, Sex, Age, SibSp, Parch, Fare, Embarked, etc.
- **Missing Data**:
  - Age → ~19.9% missing
  - Cabin → ~77% missing
  - Embarked → ~0.2% missing

---

### 3. Methodology

- **Data Profiling**: `.info()`, `.describe()`, and missing-value heatmaps
- **Univariate Analysis**: Histograms for Survived, Pclass, Age, Sex, Fare, Embarked
- **Bivariate Analysis**: Survival rates compared across Pclass, Sex, Age groups, Embarkation point, Family Size
- **Multivariate Analysis**: Correlation Matrix and Pairplots for numeric features
- **Feature Engineering**:  
  - `FamilySize` (SibSp + Parch + 1)  
  - Extracted `Title` (Mr, Miss, Mrs, etc.) from names
- **Report Writing**: Document insights under each stage

---

### 4. Key Findings

#### 4.1 Missing Value Insights
- **Age**: Missing ages were non-random; older passengers more likely to have missing values.
- **Cabin**: Dropped due to high missing rate but suggested for future text analysis.

#### 4.2 Univariate Patterns
- Survival Rate ≈ **38%**
- Class:
  - Pclass 1: ≈63% survival
  - Pclass 3: ≈24% survival
- Gender:
  - Female: ≈75% survived
  - Male: ≈20% survived
- Age:
  - Children (<16 years) had slightly better chances.
  - Median Age ≈28
- Fare:
  - Right-skewed; higher fares correlated with better survival chances.
- Embarked:
  - Cherbourg (C): Highest survival (~55%)

#### 4.3 Bivariate Relationships
- **Pclass vs. Survival**: Clear decline in survival from Pclass 1 → 3
- **Sex vs. Survival**: Major gender gap in survival rates
- **Age vs. Survival**: Children survived more; adults faced lower rates
- **Family Size**:
  - Solo travelers and very large families had lower survival.
  - Family sizes of 2–4 performed best.

#### 4.4 Multivariate Correlation
- **Pclass** negatively correlated with **Fare** and **Survival**.
- Higher **Fare** positively linked with survival chances.
- **Pairplots** showed clustering of survivors among higher fares and younger ages.

---

### 5. Recommendations
- **Impute Missing Ages**: Use median values grouped by Title (Mr, Mrs, etc.)
- **Engineer Cabin Features**: Use first letter of Cabin code for deck identification.
- **Focus on Top Predictors**:  
  - `Sex`
  - `Pclass`
  - `Fare`
  - `FamilySize`
- These features should be emphasized in future predictive modeling pipelines.

---

## 💬 LinkedIn Project Sharing Tip!

If you want to showcase this project on LinkedIn, here's a sample post idea:

> 🚢 Just completed an in-depth Exploratory Data Analysis (EDA) project on the Titanic dataset!  
> 
> 📊 Explored demographic and ticket-based factors affecting survival chances.  
> 
> 📈 Visualized survival rates by gender, class, and embarkation.  
> 
> 🔥 Key Insights:
> - Female passengers had a ~75% survival rate!
> - Children (<16) had higher survival odds.
> - Higher fares and first-class tickets boosted survival probability.
> 
> 👉 Applied feature engineering by creating FamilySize and extracting passenger Titles.  
> 
> Excited to build predictive models on top of this next!  
> 
> #DataScience #EDA #Titanic #Python #Seaborn #Pandas #DataAnalytics

---

📤 **Final Deliverables**:
- `task5.ipynb` (EDA code and findings)
- (Optional) Exported `report.pdf` from the notebook
