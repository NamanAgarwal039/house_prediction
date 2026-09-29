# 🐼 California Housing Study & Practice Guide

Welcome to the California Housing Analysis Repository! This repository serves as a hands-on data manipulation, visualization, and machine learning workflow using Python's `pandas`, `seaborn`, and `scikit-learn` libraries.

---

## 📁 Repository Contents & Topics Covered

The practice scripts and notebooks in this repository cover the following key Pandas & Machine Learning workflows:

| Topic / Category | Description & Methods Covered |
| :--- | :--- |
| **1. Dataset Inspection & Exploration** | `pd.read_csv()`, `df.head()`, `df.tail()`, `df.shape`, `df.describe()`, `df.info()`, `df.columns` |
| **2. Data Selection & Filtering** | Column selection (`df['median_house_value']`), conditional filtering (`df[df['median_income'] > 5.0]`) |
| **3. Feature Engineering** | Creating new ratios (`df['rooms_per_household'] = df['total_rooms'] / df['households']`) |
| **4. Updating Data** | Transforming columns (`df['median_income'] = df['median_income'] * 10000`) |
| **5. Missing Data Handling** | Checking nulls (`df.isnull().sum()`), dropping missing rows (`df.dropna(subset=['total_bedrooms'])`) |
| **6. Categorical Encoding** | One-hot encoding categorical features (`pd.get_dummies(df['ocean_proximity'])`) |
| **7. Sorting & Ranking** | Ordering records (`df.sort_values(by='median_house_value', ascending=False)`) |
| **8. Aggregation & Summarization** | Summary metrics (`.mean()`, `.median()`, `.min()`, `.max()`) |
| **9. Grouping Data** | Grouping by location factors (`df.groupby('ocean_proximity')['median_house_value'].mean()`) |
| **10. Data Visualization** | Histograms and geographical scatter plots (`sns.histplot()`, `sns.scatterplot()`) |
| **11. Model Training & Evaluation** | Splitting data (`train_test_split()`), baseline regression models (`LinearRegression()`, `mean_squared_error()`) |

---

