🐼 California Housing Study & Practice GuideWelcome to the California Housing Analysis Repository! This repository serves as a hands-on data manipulation, visualization, and machine learning workflow using Python's pandas, seaborn, and scikit-learn libraries.📁 Repository Contents & Topics CoveredThe practice scripts and notebooks in this repository cover the following key Pandas & Machine Learning workflows:Topic / CategoryDescription & Methods Covered1. Dataset Inspection & Explorationpd.read_csv(), df.head(), df.tail(), df.shape, df.describe(), df.info(), df.columns2. Data Selection & FilteringColumn selection (df['median_house_value']), conditional filtering (df[df['median_income'] > 5.0])3. Feature EngineeringCreating new ratios (df['rooms_per_household'] = df['total_rooms'] / df['households'])4. Updating DataTransforming columns (df['median_income'] = df['median_income'] * 10000)5. Missing Data HandlingChecking nulls (df.isnull().sum()), dropping missing rows (df.dropna(subset=['total_bedrooms']))6. Categorical EncodingOne-hot encoding categorical features (pd.get_dummies(df['ocean_proximity']))7. Sorting & RankingOrdering records (df.sort_values(by='median_house_value', ascending=False))8. Aggregation & SummarizationSummary metrics (.mean(), .median(), .min(), .max())9. Grouping DataGrouping by location factors (df.groupby('ocean_proximity')['median_house_value'].mean())10. Data VisualizationHistograms and geographical scatter plots (sns.histplot(), sns.scatterplot())11. Model Training & EvaluationSplitting data (train_test_split()), baseline regression models (LinearRegression(), mean_squared_error())🚀 Quick Reference & Code Examples1. Data Loading & ExplorationPythonimport pandas as pd
import numpy as np

# Load dataset from data directory
df = pd.read_csv("data/housing.csv")

# Quick inspection
print("Shape:", df.shape)
print("Columns:", df.columns.tolist())
display(df.head())
display(df.info())
print(df.describe())
2. Missing Value Handling & Feature EngineeringPython# Check for missing values
print("Missing values per column:")
print(df.isnull().sum())

# Clean missing bedroom entries
df_clean = df.dropna(subset=["total_bedrooms"]).copy()

# Engineer aggregate spatial and household features
df_clean["rooms_per_household"] = df_clean["total_rooms"] / df_clean["households"]
df_clean["bedrooms_per_room"] = df_clean["total_bedrooms"] / df_clean["total_rooms"]
df_clean["population_per_household"] = df_clean["population"] / df_clean["households"]
3. Grouping & Model PreparationPythonfrom sklearn.model_selection import train_test_split

# Grouped target summary
ocean_val = df_clean.groupby("ocean_proximity")["median_house_value"].mean()
print(ocean_val)

# Separate features and target label
X = df_clean.drop(columns=["median_house_value"])
y = df_clean["median_house_value"]

# Train/Test Split (80/20)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
print(f"Train size: {len(X_train)} | Test size: {len(X_test)}")
