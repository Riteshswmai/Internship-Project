# # Motor Speed Prediction using Machine Learning (Internship-Project)

## 📌 Overview
This project focuses on the Exploratory Data Analysis (EDA) of a Motor Speed Dataset, which contains [1,330,816] rows and 12 key features related to motor performance. The analysis aims to identify patterns, trends, and relationships within the data to enhance predictive modeling.

## Dataset Features
- **Ambient Temperature**
- **Coolant Temperature**
- **Voltage (u_d, u_q)**
- **Motor Speed**
- **Torque**
- **Current (i_d, i_q)**
- **Various Temperature Readings (PM, Stator Yoke, Tooth, Winding)**

### Data Quality
- No missing (null) values.
- No duplicate rows, ensuring data integrity for further analysis.

## 📊 Exploratory Data Analysis (EDA)
EDA is the initial step in data analysis that helps understand the structure, patterns, relationships, and quality of the data before applying complex algorithms. Key components include:

### Data Cleaning
- Handling missing values, outliers, and errors.

###  📈 Sample Size Trends Over Time
- **Trend:** Sample sizes start at 81 and decrease over 7 hours, with fluctuations (e.g., drop from 36 to 32).
- **Range:** Sizes vary from 1 to 81 per profile ID.
- **Recommendation:** Improve consistency in data collection and monitor sample sizes regularly.

![Sample Size Trends](path/to/your/image.png) <!-- Replace with the actual path to your image -->

### Correlation Heatmap
- **Strong Positives:** Stator components (yoke, tooth, winding) highly correlated (0.86–0.97).
- **Strong Negatives:** Torque and i_d inversely related (-0.70).
- **Weak/No Correlation:** Ambient and i_d near-zero (0.02).

### Histogram Distributions
- **Ambient:** Peaks at 10–30 (normal/skewed).
- **Coolant:** Right-skewed, peaks at 20–60.
- **Motor Speed:** Uniform spread (0–100).
- **Torque:** Symmetrical around 0.
- **Stator Yoke:** Bimodal, peaks at 20–100.

### Outlier Handling with IQR & Trimming
- **Method Used:** IQR (Interquartile Range).
- **Impact:** Outliers removed: 67,621 rows (5%).
- **Final Dataset:** 1,263,195 rows.

## Predictive Power Score (PPS) Analysis for Motor Speed
### Top 5 Features Affecting Motor Speed
1. i_q (Quadrature-axis current) → 0.507
2. i_d (Direct-axis current) → 0.479
3. Torque → 0.479
4. u_q (Quadrature-axis voltage) → 0.472
5. u_d (Direct-axis voltage) → 0.427

## Model Building
### Random Forest
- **Model Training:** Random forest regressor initialized with 20 trees.
- **Performance Metrics:**
  - R² score: 0.9998
  - Mean Squared Error (MSE): 0.0002
  - Root Mean Squared Error (RMSE): 0.0142

### Neural Network
- **Model Overview:** 
  - Input Layer: 64 neurons (ReLU activation)
  - Hidden Layer 1: 128 neurons (ReLU activation) with Dropout (20%)
  - Hidden Layer 2: 64 neurons (ReLU activation)
  - Output Layer: 1 neuron
- **Performance Metrics:**
  - MSE: 0.0327
  - RMSE: 0.1809
  - R² Score: 0.9673

### Multiple Linear Regression
- **Performance Metrics:**
  - MSE: 0.0562
  - RMSE: 0.2371
  - R² score: 0.9439

### Conclusion of Model Building
- **Best Performing Model:** Random Forest (R²: 0.9998, RMSE: 0.0138).
- **Moderate Performance:** KNN and LGBM.
- **Poor Performing Models:** Linear Regression and Neural Networks.

## 🤖 Machine Learning Models & Performance

| Model                 | R² Score | MSE   | RMSE  |
|----------------------|---------|-------|-------|
| **Random Forest**    | **0.9998**  | 0.0002 | 0.0142 |
| Decision Tree        | 0.9996  | 0.0004 | 0.0201 |
| XGBoost             | 0.9995  | 0.0005 | 0.0222 |
| LightGBM            | 0.996   | 0.0039 | 0.0300 |
| Neural Network      | 0.9673  | 0.0327 | 0.1809 |
| Multiple Linear Regression | 0.9439  | 0.0562 | 0.2371 |

### 🏆 Best Performing Model: **Random Forest**
- Highest **R² (0.9998)** and lowest **RMSE (0.0142)**

## 🚀 Model Deployment
### Overview
A Streamlit application designed to predict motor speed based on various operational parameters.

### User Instructions
1. Adjust the slider values for each parameter.
2. Click the "Predict Motor Speed" button.
3. View the predicted motor speed and modify inputs for different scenarios.

## Conclusion
This project successfully predicted motor speed using machine learning, focusing on data preprocessing, model selection, and deployment. Future improvements include real-time sensor data, advanced models
