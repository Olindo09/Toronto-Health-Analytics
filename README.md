# Toronto Crime Analytics & Prediction

This repository contains two Jupyter notebooks that analyze and forecast Toronto crime statistics using pandas/GeoPandas for data wrangling, Folium for interactive maps, and multiple ML models (XGBoost, Gradient Boosting, Random Forest, Linear/Logistic Regression from scikit-learn).

## Notebooks

### 1) `Gson Data Analytics Toronto Crime Statistics.ipynb`
**What it does**
- Loads **Assault** data (expects `Assault.csv`).
- Cleans/joins geospatial data with **GeoPandas** and renders an interactive **Folium** map.
- Trains an **XGBoost Regressor** to predict `ASSAULT_2023` by area.
- Computes **MSE** and **R²** and builds an “Actual vs Predicted” table.

**Key libraries**
- `pandas`, `geopandas`, `folium`
- `xgboost`/`sklearn` (XGBRegressor usage is present)
- (Notebook also imports `panel`, `pyngrok`, `gradio`, `jupyter_bokeh` but core flow is Folium + model scoring.)

**Expected data**
- `/mnt/data/Assault.csv` (or provide `Assault.csv` in a local `data/` folder and update the path in the notebook)

---

### 2) `Toronto Crime Statiscal Prediction.ipynb`
**What it does**
- Works with **AutoTheft** and **Assault** datasets (in Colab it uses `google.colab.files.upload()`).
- Trains and compares:
  - **GradientBoostingRegressor**
  - **RandomForestRegressor**
  - **LinearRegression**
- Uses **train/test split**, **cross-validation**, **GridSearchCV**.
- Exports:
  - `Cross_Validation_Results.csv`
  - `Model_Performance_Summary.csv`
  - `Assault_Actual_vs_Predicted_Errors_Accuracy.csv`
  - `AutoTheft_Actual_vs_Predicted_Errors_Accuracy.csv`
- Saves comparison plots to `/mnt/data/plots` (uses `matplotlib` and `seaborn`).

**Key libraries**
- `pandas`, `numpy`
- `scikit-learn` (modeling, metrics, CV, grid search)
- `matplotlib`, `seaborn`
- (Uses `os`, `zipfile` for organizing/saving outputs)

---

## Project Goals
- **EDA & Mapping:** Explore spatial/temporal patterns (Assaults by area; Folium interactive map).
- **Forecasting:** Predict crime counts by area/period with tree-based and linear models.
- **Evaluation:** Report **MSE, MAE, RMSE, R²**; compare model families; export clean CSV summaries.

---

## Repository Structure
