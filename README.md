# DULHARA_KAUSHALYA_ROP_PREDICTION

This project centers on the `ROP_predict_model.ipynb` notebook. Below is a concise walkthrough of what you did in the notebook so others (or future you) can quickly understand the workflow:

1. Data loading
	- The notebook reads a CSV file (example path in the notebook: `/content/Data-Set-AI-ML-Assignment-1.csv`). The expected columns are: `well`, `depth`, `RPM`, `Flow`, `WOB`, `ROP`.

2. Exploratory Data Analysis (EDA)
	- Displayed data summary and data types.
	- Plotted histograms, pairplots and a correlation heatmap to inspect relationships.
	- Checked for duplicates and missing values.

3. Preprocessing and feature engineering
	- Dropped the non-predictive `well` column.
	- Removed duplicate rows and reset the index.
	- Smoothed noisy signals (`RPM`, `Flow`, `WOB`) using a Savitzky–Golay filter.
	- Created physics-inspired features: `Mechanical_Power`, `Hydraulic_Force`, and `MSE_Proxy`.

4. Train/test split and scaling
	- Split the processed data into training and test sets (`test_size=0.2`, `random_state=42`, `shuffle=True`).
	- Standard scaled feature columns with `StandardScaler`.

5. Model training and benchmarking
	- Defined and trained multiple regression models: Linear Regression, Random Forest, XGBoost, and an MLP neural network.
	- Evaluated each model using RMSE and R2 on the test set and identified the best-performing model.

6. Hyperparameter tuning
	- Set up parameter grids for Random Forest, XGBoost, and Neural Network.
	- Used `RandomizedSearchCV` to tune the best model (if a tuning grid exists for the chosen model).

7. Final evaluation and visualization
	- Generated final predictions using the tuned model.
	- Calculated final RMSE and R2 metrics and plotted Actual vs Predicted values.

8. Save model and scaler
	- Saved the tuned model and scaler to disk as `best_rop_model_tuned.pkl` and `rop_model_scalar.pkl`. 

