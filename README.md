# QuickCart Stockout Risk Prediction

## Project Overview
QuickCart Stockout Risk Prediction is a supervised machine learning project that predicts inventory stockout risk for products across multiple stores. The objective is to identify products that may run out of stock before the next supplier delivery arrives.

The model classifies inventory into three categories:
- **Safe**
- **At-Risk**
- **Imminent**

## Objectives
- Analyze inventory data from multiple related tables.
- Clean missing values and inconsistent data.
- Perform exploratory data analysis (EDA).
- Engineer features related to inventory levels and supplier lead times.
- Train and evaluate multiclass classification models.
- Improve detection of high-risk inventory using probability threshold adjustment.

## Dataset
The project uses five CSV files:
- `dim_stores.csv`
- `dim_skus.csv`
- `dim_suppliers.csv`
- `dim_events.csv`
- `fact_inventory_daily.csv`

The combined dataset contains **21,600 inventory records** covering 12 stores, 60 SKUs, and 30 days.

## Data Preparation and Feature Engineering
- Standardized inconsistent city-name capitalization.
- Converted supplier reliability scores to numeric values and handled missing values.
- Joined the five tables using their relevant keys.
- Created `reorder_gap`, `days_of_cover_ratio`, `day_of_month`, and `days_since_festival_start`.
- Encoded categorical variables and prepared numerical features for machine learning.

## Machine Learning Models
The following approaches were evaluated:
- Majority-class baseline
- Logistic Regression
- Random Forest
- Random Forest with class weighting and probability threshold adjustment

A time-based split was used: October 1–23, 2026, for training and October 24–30, 2026, for testing.

## Results
The tuned Random Forest model with an Imminent probability threshold of 0.30 achieved approximately:

- **Accuracy:** 94.29%
- **Safe recall:** 1.00
- **At-Risk recall:** 0.88
- **Imminent recall:** 0.82

These results were obtained on the held-out test period. Performance on new real-world inventory data may differ.

## Technologies Used
- Python
- Pandas and NumPy
- Scikit-learn
- Matplotlib and Seaborn
- Google Colab
- Joblib

## Key Learning Outcomes
- Multi-table data integration
- Data cleaning and preprocessing
- Feature engineering
- Multiclass classification
- Time-based model evaluation
- Class imbalance handling
- Probability threshold tuning
- Model saving and reuse

## Conclusion
This project demonstrates how machine learning can support inventory risk monitoring by identifying products that may require earlier replenishment. It also highlights why class-specific recall and business priorities matter alongside overall accuracy.

