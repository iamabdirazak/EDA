# 🥾 Trail Risk Predictor

This project builds a linear regression model to predict trail risk based on features like distance, elevation, terrain type, and danger level. It includes Exploratory Data Analysis (EDA), preprocessing, model training, and prediction.

## 📂 Dataset

The dataset includes:

- `distance`: Trail distance (meters)
- `elevation`: Elevation gain (meters)
- `terrain`: Type of terrain (`dirt`, `sand`, `rocky`, etc.)
- `dangerous`: Binary indicator if the trail is known to be dangerous
- `risk`: Risk score (target variable)

## 🧪 Techniques Used

### ✅ Exploratory Data Analysis (EDA)

- Summary statistics (`.describe()`)
- Missing value check
- Visualizations:
  - Risk distribution
  - Boxplots (terrain vs risk)
  - Correlation heatmap

### ✅ Data Preprocessing

- One-hot encoding for `terrain`
- Alignment of features across training and testing sets
- Normalization and risk level categorization for prediction readability

### ✅ Modeling

- Linear Regression (`sklearn`)
- Training on 10k dataset, tested on 1k dataset
- Evaluation using:
  - Mean Squared Error (MSE)
  - R² Score

### ✅ Model Persistence

- Saved model with `joblib`
- Loaded model for real-time prediction using new trail input data

## 📈 Prediction Output

Predicted risk is normalized to a score out of 100 and categorized as:

- **Low Risk**
- **Moderate Risk**
- **High Risk**
- **Very High Risk**

## ▶️ Example Usage

```python
# Load model
model = joblib.load("trail_risk_model.pkl")

# Prepare new trail input
new_data = {
    "distance": 50,
    "elevation": 200,
    "terrain": "rocky",
    "dangerous": 0
}

# Predict and interpret risk
# (see script for full pipeline)
```
