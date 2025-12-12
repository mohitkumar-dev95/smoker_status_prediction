# 🚬 Smoker Status Prediction (Binary Classification)

This project predicts whether an individual is a **smoker (1)** or **non-smoker (0)** using biomedical, physiological, and lifestyle-related features. The dataset undergoes extensive **feature engineering**, **preprocessing**, and model evaluation using **Logistic Regression**, **SVM**, and a **Neural Network**.

---

## 👨‍💻 Contributors

- **Aman Tiwari (MT2025018)**
- **Mohit Kumar (MT2025075)**

GitHub Links:  
- Aman: https://github.com/Aman-dps/Smoker_Detection  
- Mohit: https://github.com/mohitkumar-dev95/smoker_status_prediction  

---

## 📁 Repository Structure


---

## 📊 Dataset Overview

- **Total Records:** 38,984  
- **Features:** 23 original + engineered features  
- **Target Variable:** `smoking` (0 = non-smoker, 1 = smoker)  
- **No missing values** were detected.  

### Class Distribution:
- **Non-smokers:** ~63.3%  
- **Smokers:** ~36.7%

---

## 🧪 Exploratory Data Analysis (EDA)

Key findings:

- Most physical attributes (age, height, waist, blood pressure) resemble normal distributions.  
- Some features (triglycerides, fasting sugar, creatinine, GTP) show **high skew**.  
- Lipid panel components correlate with smoking behavior.

---

## 🛠 Feature Engineering

New engineered features added:

| Feature | Description |
|--------|-------------|
| **BMI** | weight(kg) / (height(m))² |
| **avg_eyesight** | (eyesight_left + eyesight_right) / 2 |
| **hearing_impaired** | 1 if either ear impaired |
| **pulse_pressure** | systolic – relaxation |
| **chol_hdl_ratio** | cholesterol / HDL |
| **ast_alt_ratio** | AST / ALT |

Additional binary indicators (diabetes, anemia, liver damage, etc.) were explored.

---

## 🧹 Data Preprocessing

Steps:

- Selected all numerical & engineered columns for **X**
- Target variable **y = smoking**
- Applied **StandardScaler** on all numeric features  
- Split data: **80% train / 20% test**

---

## 🤖 Model Building

Three models were trained:

---

### 1️⃣ Logistic Regression

- Accuracy: **72.57%**
- Precision: **63.31%**
- Recall: **57.55%**
- F1-score: **60.29%**

A strong, interpretable baseline.

---

### 2️⃣ Support Vector Machine (Linear Kernel)

- Accuracy: **51.83%**
- Precision: **41.94%**
- Recall: **86.11%**
- F1-score: **56.41%**

High recall but low precision  
Model struggled with linear decision boundary.

---

### 3️⃣ Neural Network (Best Model)



Performance:

- Accuracy: **75.79%**
- Precision: **67.54%**
- Recall: **63.71%**
- F1-score: **65.57%**

Best at capturing complex relationships.

---

## 📈 Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 0.7257 | 0.6331 | 0.5755 | 0.6029 |
| **Neural Network** | **0.7579** | **0.6754** | **0.6371** | **0.6557** |
| SVM | 0.5183 | 0.4194 | **0.8611** | 0.5641 |

✔ Neural Network is the best overall  
✔ SVM finds smokers well but misclassifies many non-smokers  
✔ Logistic Regression is balanced & interpretable

---

## 🧮 Evaluation Metrics Explained

### Accuracy
Overall correctness of predictions.

### Precision
Out of predicted smokers → how many are actual smokers?

### Recall
Out of actual smokers → how many did the model catch?

### F1 Score
Harmonic mean of precision & recall (good for imbalanced datasets).

---

## 🏁 Final Summary & Conclusion

- Feature engineering (BMI, ratios, eyesight, liver markers, etc.) improved model performance.
- Neural Network outperformed all models.
- SVM requires hyperparameter tuning and a non-linear kernel.
- Logistic Regression remains useful for interpretability.

### Future Work:
- Tune Neural Network hyperparameters using scikeras + RandomizedSearchCV  
- Explore RBF kernel SVM  
- Address class imbalance with SMOTE / class weights  
- Deploy using FastAPI or Flask  
- Add model explainability (SHAP/LIME)

---

## 🚀 How to Run

```bash
# Clone repository
git clone <your-repo-url>

# Install dependencies
pip install -r requirements.txt

# Run model training
python src/train.py


pandas
numpy
scikit-learn
matplotlib
tensorflow
keras
seaborn


Architecture:

