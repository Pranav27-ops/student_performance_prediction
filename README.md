# 🎓 Cloud-Based Student Performance Prediction System

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/student-performance-prediction/blob/main/Student_Performance_Prediction_System.ipynb)
[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow)](https://www.tensorflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **BTP2CSE339** — Minor Project | IILM University, Greater Noida  
> School of Computer Science & Engineering | Session 2025–26

---

## 👥 Team

| Name | Roll No. | Branch |
|------|----------|--------|
| Pranav Patel | 2410031387 | 2CSE22 |
| Krish Gupta | 2410031425 | 2CSE22 |
| Aniket Tiwari | 2410031403 | 2CSE22 |
| Sushant Jha | 2410031391 | 2CSE22 |
| Harshit Bhardwaj | 2410031418 | 2CSE22 |

**Guide:** Mr. Vikas Tiwari

---

## 📌 Project Overview

Traditional student performance tracking is **reactive** — educators only identify at-risk students *after* they fail. This project builds a **proactive, cloud-ready prediction system** that:

- Ingests multi-dimensional LMS + SIS student data
- Trains a **Bidirectional LSTM + GRU** deep learning model to detect at-risk students *before* failure
- Applies **SHAP (Explainable AI)** to explain *why* a student is flagged
- Provides an **interactive Educator Dashboard** with live risk alerts

---

## 🏗️ System Architecture

```
SIS Data + LMS Logs
        │
        ▼
┌─────────────────────┐
│  Cloud Data Lake     │  ← AWS S3 / Google Cloud Storage
│  (Phase 1)          │
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  Preprocessing       │  ← kNN Imputation, SMOTE, ANOVA F-Test
│  (Phase 2)          │
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  ML / DL Models      │  ← Random Forest, XGBoost, BiLSTM+GRU
│  (Phase 3)          │
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  Explainable AI      │  ← SHAP Waterfall + Beeswarm Plots
│  (Phase 4)          │
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  Educator Dashboard  │  ← Risk Alerts, Cohort Analytics, Student Lookup
│  (Phase 5)          │
└─────────────────────┘
```

---

## 📋 Project Pipeline

| Phase | Description | Key Techniques |
|-------|-------------|----------------|
| **Phase 1** | Data Acquisition & Synthetic LMS Dataset | SIS + LMS simulation, concept drift |
| **Phase 2** | Preprocessing & Feature Engineering | kNN Imputation, SMOTE, ANOVA F-Test |
| **Phase 3** | Algorithmic Modelling | Random Forest, XGBoost, BiLSTM + GRU |
| **Phase 4** | Explainable AI (XAI) | SHAP TreeExplainer, Waterfall plots |
| **Phase 5** | Educator Dashboard | Plotly, risk alerts, student lookup widget |

---

## 🛠️ Tech Stack

**Languages**
- Python 3.10+, JavaScript/TypeScript (production frontend)

**Machine Learning & Deep Learning**
- TensorFlow / Keras — BiLSTM + GRU architecture
- Scikit-Learn — preprocessing, Random Forest, evaluation
- XGBoost — gradient boosted ensemble baseline

**Explainability (XAI)**
- SHAP — TreeExplainer, Waterfall & Beeswarm plots

**Data Engineering**
- imbalanced-learn — SMOTE oversampling
- pandas, NumPy — data manipulation

**Visualization & Dashboard**
- Plotly — interactive charts
- Matplotlib / Seaborn — training history & analytics
- ipywidgets — live student lookup tool

**Cloud & DevOps (Production)**
- AWS EC2 + S3 / Google Cloud Platform
- Docker — containerization
- FastAPI — REST API serving
- React.js / Next.js — frontend educator dashboard

---

## 🚀 How to Run

### ▶️ Option 1 — Google Colab (Recommended, zero setup)

Click the badge at the top of this README, or:

1. Go to [colab.research.google.com](https://colab.research.google.com)
2. File → Open notebook → GitHub tab
3. Paste this repo URL and open `Student_Performance_Prediction_System.ipynb`
4. Click **Runtime → Run all**

> All dependencies are installed automatically in the first cell.

### 💻 Option 2 — Run Locally

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/student-performance-prediction.git
cd student-performance-prediction

# 2. Create a virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter
jupyter notebook Student_Performance_Prediction_System.ipynb
```

---

## 📦 Requirements

```
tensorflow>=2.12
scikit-learn>=1.3
xgboost>=1.7
imbalanced-learn>=0.11
shap>=0.42
pandas>=2.0
numpy>=1.24
matplotlib>=3.7
seaborn>=0.12
plotly>=5.14
ipywidgets>=8.0
```

> A `requirements.txt` is included in this repository.

---

## 📊 Results

| Model | Accuracy | ROC-AUC |
|-------|----------|---------|
| Random Forest | ~0.84 | ~0.91 |
| XGBoost | ~0.86 | ~0.93 |
| **BiLSTM + GRU** | **~0.88** | **~0.95** |

> Results may vary slightly due to random seed and synthetic data generation.

---

## 🔍 Sample SHAP Explanation

The system generates human-readable alerts like:

```
⚠️  Student STU0142 flagged at 78% failure risk due to:
    • avg_quiz_score    : SHAP = -0.412  (well below cohort average)
    • lms_logins_week   : SHAP = -0.298  (40% drop over last 2 weeks)
    • attendance_pct    : SHAP = -0.187  (attendance fallen to 54%)
→ Recommendation: Schedule academic counselling session this week.
```

---

## 📁 Repository Structure

```
student-performance-prediction/
│
├── Student_Performance_Prediction_System.ipynb   # Main Colab notebook
├── README.md                                      # This file
├── requirements.txt                               # Python dependencies
└── assets/                                        # (Optional) saved plots
    ├── phase2_preprocessing.png
    ├── phase3_training.png
    ├── phase4_shap_global.png
    └── phase5_cohort_analytics.png
```

---

## 🔮 Future Work

- Deploy as a live REST API using **FastAPI + Docker** on AWS/GCP
- Integrate real **OULAD dataset** (Open University Learning Analytics)
- Add **federated learning** for privacy-preserving multi-institution training
- Build a production **React.js dashboard** with real-time WebSocket updates
- Extend to **multi-class prediction** (Distinction / Pass / Fail / Withdrawn)

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

<p align="center">Made with ❤️ by Team BTP2CSE339 | IILM University, Greater Noida</p>
