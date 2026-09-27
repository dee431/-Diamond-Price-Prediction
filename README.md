# -Diamond-Price-Prediction
https://encrypted-tbn3.gstatic.com/licensed-image?q=tbn:ANd9GcRB7MHCkme7-pq_N1xtblrpEo9p2rPC2QAtZZSyJZ001v46Bckbw9R_1dXQxaA1V-joIESx4ngNyct3rhQ
Markdown
# 💎 GemVal: End-to-End Diamond Price Prediction System

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

> *Unveiling the true worth of brilliance through Machine Learning.*

---

## 🚀 Overview

The **Diamond Price Prediction** project is a modular, production-grade Machine Learning pipeline designed to estimate the market value of diamonds based on their physical dimensions and quality ratings. By analyzing geometric attributes alongside gemstone metrics (the famous **4Cs**), this system eliminates guesswork and provides real-time pricing estimates.

### ✨ Key Highlights
- **End-to-End Pipeline**: Modular code structure (`Ingestion` ➔ `Transformation` ➔ `Model Training` ➔ `Inference`).
- **Data Engineering**: Robust handling of ordinal categoricals, numerical scaling, and skewness treatment.
- **Multi-Model Evaluation**: Evaluated across Linear, Ridge, Lasso, Decision Trees, and Random Forest regressors.
- **Production Ready**: Includes custom logging, centralized exception handling, artifact management, and a web deployment interface.

---

## 📊 Dataset & Feature Architecture

The model predicts the `price` (in USD) using 9 core physical features:

| Feature | Type | Description |
| :--- | :--- | :--- |
| **Carat** | Continuous | Weight of the diamond (1 carat = 200 mg) |
| **Cut** | Categorical (Ordinal) | Quality of cut (`Fair`, `Good`, `Very Good`, `Premium`, `Ideal`) |
| **Color** | Categorical (Ordinal) | Diamond color grade from `J` (worst/yellowish) to `D` (best/colorless) |
| **Clarity** | Categorical (Ordinal) | Inclusion scale (`I1`, `SI2`, `SI1`, `VS2`, `VS1`, `VVS2`, `VVS1`, `IF`) |
| **Depth %** | Continuous | Total depth percentage = $z / mean(x, y) = 2 \times z / (x + y)$ |
| **Table %** | Continuous | Width of top of diamond relative to widest point |
| **x** | Continuous | Length in mm |
| **y** | Continuous | Width in mm |
| **z** | Continuous | Depth in mm |

---

## 📂 Repository Structure

```text
├── artifacts/              # Saved model pickles, preprocessor objects, & raw data
├── notebook/               # Exploratory Data Analysis & Model Training Experiments
│   ├── EDA_Diamonds.ipynb
│   └── Model_Training.ipynb
├── src/                    # Core source code
│   ├── components/         # Pipeline building blocks
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   ├── pipeline/           # Execution pipelines
│   │   ├── predict_pipeline.py
│   │   └── train_pipeline.py
│   ├── exception.py        # Custom exception logging
│   ├── logger.py           # Centralized logging setup
│   └── utils.py            # Helper functions & artifact savers
├── templates/              # HTML frontend for Flask web app
│   └── index.html
├── app.py                  # Entry point for Web API
├── requirements.txt        # Project dependencies
└── setup.py                # Package installer configuration
🛠️ Getting Started
Prerequisites
Python 3.8 or higher
Git installed on your system
Installation Steps
Clone the Repository
Bash
git clone [https://github.com/dee431/-Diamond-Price-Prediction.git](https://github.com/dee431/-Diamond-Price-Prediction.git)
cd -Diamond-Price-Prediction
Create a Virtual Environment
Bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install Dependencies
Bash
pip install -r requirements.txt
Train the Pipeline
Bash
python src/pipeline/train_pipeline.py
Launch the Web Application
Bash
python app.py
Open your browser and navigate to http://127.0.0.1:5000 to interact with the price prediction portal!
⚡ Pipeline Architecture
Plaintext
┌─────────────────┐      ┌──────────────────────┐      ┌──────────────────┐
│  Data Ingestion │ ───► │ Data Transformation  │ ───► │  Model Training  │
└─────────────────┘      └──────────────────────┘      └──────────────────┘
                                   │                            │
                            Ordinal Encoding             Model Selection
                             StandardScaler               Artifact Export
                                   │                            │
                                   ▼                            ▼
                         preprocessor.pkl                  model.pkl
                                   │                            │
                                   └──────────────┬─────────────┘
                                                  ▼
                                       ┌────────────────────┐
                                       │ Prediction Engine  │
                                       └────────────────────┘
📈 Model Performance
Multiple regression models were evaluated on the validation dataset:
Random Forest Regressor: Best balance of low RMSE & High R 
2
  Score (>97%).
Linear / Ridge / Lasso Regression: Baseline validation for linear dependencies.
👨‍💻 Author
Deepanshu
Computer Science & Engineering (AI & ML)
GitHub: @dee431
If you find this project useful, feel free to give it a ⭐️ on GitHub!
