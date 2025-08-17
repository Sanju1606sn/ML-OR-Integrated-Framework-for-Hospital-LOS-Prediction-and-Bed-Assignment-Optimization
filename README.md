# ML-OR-Integrated-Framework-for-Hospital-LOS-Prediction-and-Bed-Assignment-Optimization
Hospital Length of Stay Prediction & Bed Assignment Optimization

This project combines machine learning and mathematical optimization to address one of the most critical challenges in healthcare: efficient hospital bed management. By predicting how long a patient is likely to remain hospitalized, we can allocate limited resources more effectively, reduce bottlenecks, and improve patient flow.

The project leverages real-world discharge data and applies both predictive modeling and optimization techniques to balance accuracy with computational efficiency.

#  Project Overview

Objective:
To predict the Length of Stay (LOS) of patients using machine learning models and then apply these predictions to optimize hospital bed allocation using mathematical programming and heuristics.

Data Source:
SPARCS – New York State Hospital Inpatient Discharges, a large-scale dataset containing de-identified inpatient hospital records.

Key Tools & Libraries:

Machine Learning: scikit-learn, XGBoost

Optimization: PuLP (Mixed-Integer Linear Programming), custom greedy heuristic

Data Handling & Visualization: Python (pandas, numpy), seaborn, matplotlib

#  Workflow
# 1. Exploratory Data Analysis (EDA) & Cleaning

File: 01_EDA_and_Cleaning.ipynb

Performed data cleaning, removal of missing values, and feature engineering.

Encoded categorical variables and standardized numerical ones for modeling readiness.

# 2. LOS Prediction Modeling

File: 02_Modeling_LOS_Prediction.ipynb

Tested multiple models: Linear Regression, Random Forest, and XGBoost.

Best Model: XGBoost, after applying one-hot encoding and scaling.

Provided the most balanced performance in terms of error and generalization.

# 3. Bed Assignment Optimization (MILP)

File: 03_Optimization_Bed_Management.ipynb

Formulated as a Mixed-Integer Linear Programming (MILP) problem.

Objective: minimize idle time and overlap in bed assignments while ensuring all patients are allocated appropriately.

Provides optimal allocation, but can become computationally heavy for large datasets.

# 4. Heuristic Bed Assignment

File: 04_Heuristic_Bed_Assignment.ipynb

Implemented a greedy algorithm to quickly assign patients to beds.

Sacrifices some optimality for speed and scalability.

Benchmarked performance against MILP across different patient sizes.

# Results
🔹 LOS Prediction

Final Model: XGBoost

Performance Metrics:

RMSE ≈ 6.71 days

MAE ≈ 3.21 days

R² ≈ 0.3710

These results provide a baseline for LOS prediction. While not perfect, they establish a strong foundation. Incorporating richer feature sets (e.g., medical history, hospital-specific factors) or advanced deep learning models could further improve accuracy.

# Optimization & Heuristic Benchmark
Patients	Beds Used	Idle Time (%)	Runtime (s)
200	30	~34.8%	< 0.1 s
500	63	~26.1%	< 0.1 s

MILP (Optimal): Guarantees the best possible allocation but requires more computation, especially for large-scale hospital data.

Greedy Heuristic (Approximate): Produces near-optimal solutions in fraction of a second, making it suitable for real-time or large hospital operations.

 Together, the two approaches provide both theoretical optimality and practical scalability, depending on the operational need.

Would you like me to also add a “Key Insights & Impact” section here (something like an executive summary highlighting what these results mean for real hospital operations)? That could make the README more persuasive for non-technical readers.
