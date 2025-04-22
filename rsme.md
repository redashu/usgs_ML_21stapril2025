# Understanding MSE and RMSE in Earthquake Prediction

## 1. What MSE Represents

**Definition**: The Mean Squared Error (MSE) is the average of the squared differences between predicted (\( \hat{y} \)) and actual (\( y \)) magnitudes.

\[
MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
\]

- **Units**: Magnitude squared (e.g., if magnitudes range from 1.0 to 8.0, MSE is in units like "2.5 Richter²").

---

## 2. Interpreting Your Model’s MSE

From your earlier code:

```python
rmse = mean_squared_error(y_test, predictions, squared=False)
print(f"RMSE: {rmse:.4f}")
```

- **RMSE (Root MSE)**: Square root of MSE, easier to interpret as it has the same units as magnitude.

For example, if RMSE = 0.5, your predictions are typically ±0.5 magnitude units off.

### Context for USGS Data

| Magnitude Range       | Typical RMSE | Interpretation                     |
|------------------------|--------------|-------------------------------------|
| Microquakes (<3.0)     | 0.2–0.5      | Good for detecting small quakes.   |
| Moderate (4.0–6.0)     | 0.5–1.0      | Moderate reliability.              |
| Major (7.0+)           | 1.0+         | Challenging to predict accurately. |

---

## 3. Why MSE/RMSE?

### Advantages:
- Penalizes large errors more severely (critical for disaster prediction).
- Works well with continuous targets (like magnitude).

### Limitations:
- Sensitive to outliers (e.g., a single M8.0 misprediction skews MSE).

---

## 4. Improving Your Model

### If MSE is Too High:

#### Feature Engineering
- Add tectonic plate distances:
    ```python
    data['distance_to_plate'] = ...  # Calculate from plate boundaries
    ```
- Use temporal features (e.g., `day_of_year` from timestamps).

#### Model Tuning
- Try `XGBoost` or `GradientBoostingRegressor` (often better than Random Forest for tabular data).
- Optimize hyperparameters with `GridSearchCV`.

#### Outlier Handling
- Cap extreme magnitudes (e.g., clip `mag > 7.0` to `7.0`).

---

## 5. Code: Full Evaluation Metrics

```python
from sklearn.metrics import mean_absolute_error, r2_score

mse = mean_squared_error(y_test, predictions)
rmse = np.sqrt(mse)
mae = mean_absolute_error(y_test, predictions)
r2 = r2_score(y_test, predictions)

print(f"""
Model Performance:
- MSE: {mse:.3f} (Richter²)
- RMSE: {rmse:.3f} (Richter)
- MAE: {mae:.3f} (Robust to outliers)
- R²: {r2:.3f} (1.0 = perfect fit)
""")
```

### Output Example:
```
Model Performance:
- MSE: 0.254 (Richter²)
- RMSE: 0.504 (Richter)
- MAE: 0.412 (Robust to outliers)
- R²: 0.682 (1.0 = perfect fit)
```

---

## 6. Comparing to Baseline

**Naive Baseline**: Always predict the mean magnitude.

```python
baseline_pred = np.full_like(y_test, y_train.mean())
baseline_rmse = mean_squared_error(y_test, baseline_pred, squared=False)
print(f"Baseline RMSE (mean prediction): {baseline_rmse:.3f}")
```

Your model should outperform this!

---

## 7. When to Worry

- **RMSE > 1.0**: Poor for hazard prediction (e.g., confusing M5.0 with M6.0 is dangerous).
- **R² < 0.5**: Model explains less than 50% of variance.

---

## Key Takeaway

Your MSE/RMSE quantifies average prediction error. For USGS applications:

- **RMSE < 0.5**: Excellent for early-warning systems.
- **RMSE 0.5–1.0**: Needs improvement.
- **RMSE > 1.0**: Re-evaluate features/model.