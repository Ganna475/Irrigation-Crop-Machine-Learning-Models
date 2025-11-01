This repository contains a collection of machine learning models designed for irrigation, crop yield prediction, crop nutrition management, and crop recommendation systems. Each model is built to assist farmers, agronomists, and researchers in making data-driven decisions for improving crop productivity and nutrient management.

1. Crop Yield Prediction (Enhanced)

- Description:
Predicts crop yield based on Year and Crop Type. The model uses a Random Forest Regressor to capture non-linear relationships between crop type and yield over time.

- Features:

Year

Crop Type (one-hot encoded)

- Target:

Crop yield (Value in hg/ha)

- Preprocessing:

One-hot encoding for categorical features

Standardization of features

Train/Test split for realistic performance evaluation

- Performance:

Mean Squared Error (MSE): ~2.41e9 (baseline, can be improved with additional features)

- Usage:

The model is saved as improved_crop_yield_model.pkl for future predictions.






2. Crop Nutrition Management

- Description:
Predicts crop yield based on nutrient content and moisture, helping farmers optimize fertilization and irrigation strategies. Uses a Random Forest Regressor trained on nutrient data.

- Features:

AvN%(dry)

AvMoisture%

AvYieldUnitWeight(lb)

- Target:

AvYieldUnitWeight(lb) (yield per unit weight)

- Preprocessing:

Numeric conversion for features and target

Handling missing values with column mean

Standardization of features

- Performance:

Mean Squared Error (MSE): ~17.68

- Usage:

Saved as nutrient_management_model.pkl






3. Crop Recommendation Management

- Description:
Classifies and recommends the most suitable crop based on soil and climate conditions. Uses a Random Forest Classifier for multi-class prediction.

- Features:

N, P, K (soil nutrients)

temperature, humidity, ph, rainfall (climatic conditions)

- Target:

label (crop type)

- Preprocessing:

Label encoding for categorical crop types

Standardization of numeric features

Train/Test split

- Performance:

Accuracy: 99%

High precision and recall across all crop types

Example Usage:

input_data = [[90, 42, 43, 20.87, 82.00, 6.5, 202.93]]  # Example input
predicted_crop = model.predict(scaler.transform(input_data))







Additional Notes

- All models are implemented in Python using scikit-learn.

- Saved models are ready for deployment or further experimentation.

- Future improvements may include:

Adding more features (climate data, soil type, irrigation patterns)

Hyperparameter tuning for better performance

Using advanced ensemble methods like XGBoost or LightGBM







Repository Structure

├── crop_yield_prediction/
│   └── improved_crop_yield_model.pkl
├── crop_nutrition_management/
│   └── nutrient_management_model.pkl
├── crop_recommendation_management/
│   └── crop_recommendation_model.pkl
└── README.md
