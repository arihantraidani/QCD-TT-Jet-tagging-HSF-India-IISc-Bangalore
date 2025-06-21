# Jet Tagging – QCD vs TT Classification using Machine Learning  
**Top 10 Finalist – HSF-India 2025 Kaggle Challenge**

![Leaderboard Badge](https://img.shields.io/badge/Kaggle-Top_10-blue)  
📊 Final Score: **0.95878** | 🏁 Top Score: 0.96233

---

## 🔬 Overview

This project focuses on the classification of particle jets produced in high-energy **proton-proton collisions** at the **Large Hadron Collider (LHC)** at CERN. The goal was to build machine learning models that distinguish **QCD (Quantum Chromodynamics) background jets** from **TT (top quark pair decay) signal jets** using both **scalar features** and **jet images**.

> This repository contains my complete workflow for the **Jet Tagging Challenge** organized as part of the [HSF-India 2025 Scientific Computing Workshop](https://indico.cern.ch/event/1306925/). I placed **10th on the final leaderboard**, with a score of **0.95878**.

---

## 🧪 Physics Behind the Problem

At the LHC, when protons collide at near light speed, they produce cascades of particles. These cascades form **jets** — collimated sprays of particles moving in similar directions.

- **QCD jets**: Produced by strong force interactions (gluon or quark radiation), generally **symmetric**, with **fewer, lower-energy** clusters.
- **TT jets**: From top quark decays, typically **more energetic**, with **wider angular spread** and **asymmetric energy distribution**.

Distinguishing between the two is essential for detecting **new physics** such as **Higgs bosons** or **supersymmetric particles**, as TT jets often indicate more interesting physics beyond the Standard Model.

---

## 🧠 Project Highlights

| Model                 | Validation AUC | Public LB Score |
|----------------------|----------------|------------------|
| Logistic Regression   | 0.94218        | 0.94218          |
| XGBoost (tuned)       | 0.94393        | 0.93630          |
| DNN (tuned + CV)      | 0.94492        | 0.93633          |
| **CNN (Jet Images)**  | **~0.951**     | **0.95135** ✅    |
| Final Ensemble        | ~0.945         | 0.93596          |

---

## 🧰 Repository Structure

jet-tagging-qcd-vs-tt/
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_xgboost_model.ipynb
│   ├── 03_dnn_model.ipynb
│   ├── 04_cnn_model.ipynb
│   ├── 05_ensemble.ipynb
│
├── models/
│   ├── best_model_xgb.pkl
│   ├── best_model_dnn.h5
│   └── cnn_model_architecture.png
│
├── data/ (optional if public)
│   └── README.md → describe the Kaggle dataset link instead
│
├── submissions/
│   ├── submission_xgb.csv
│   ├── submission_dnn.csv
│   ├── submission_cnn.csv
│   └── final_submission.csv
│
├── figures/
│   ├── roc_xgb.png
│   ├── roc_dnn.png
│   ├── cnn_architecture.png
│   └── leaderboard_score.png
│
├── src/ (optional)
│   ├── preprocessing.py
│   ├── training_utils.py
│   └── ensemble.py
│
├── requirements.txt
├── LICENSE
├── .gitignore
├── README.md ✅


---

## ⚙️ Techniques Used

### ✅ Feature Engineering
- Log transforms, ratios (e.g. `pt/cluster`), angular spreads (`η`–`φ` space)
- Domain-inspired features derived from LHC jet structure

### ✅ Tabular Modeling
- Baselines: Logistic Regression, XGBoost
- Advanced: Deep Neural Network (DNN) with cross-validation

### ✅ Jet Image Modeling
- Custom-built **Convolutional Neural Network (CNN)** for 33×33 grayscale jet images
- Achieved best performance on leaderboard with CNN alone

### ✅ Model Ensembling
- Blending DNN, CNN, XGBoost, and LR predictions
- Grid search for optimal AUC weight combinations

---

## 📊 Dataset

The dataset is from the [Kaggle QCD vs TT Jet Tagging Challenge](https://www.kaggle.com/competitions/qcd-vs-tt-jet-tagging-hsf-india-bangalore/overview), and includes:

- Scalar features (`cluster_features.csv`) from anti-kT jet clustering
- Jet images (`jet_images.h5`) in (33, 33, 1) format
- Labels (`labels.npy`) and event IDs

Due to licensing, you must download the dataset directly from Kaggle.

---

## 📈 Results

- 🥇 **Final Public Leaderboard Score**: `0.95878`
- 🔟 **Top 10 in the competition**
- 🧠 Demonstrated value of combining **physics insight**, **feature engineering**, and **deep learning on jet images**

---

## 🚀 Future Work

- Combine CNN with tabular features using a hybrid neural net
- Explore Vision Transformers (ViTs) or ResNet variants for image modeling
- Tune ensembles with meta-learners (e.g. logistic stacking)
- Automate submission pipelines for experiments

---

## 👤 Author

**Arihant Raidani**    
📧 arihantraidani10@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/arihant-raidani) • [GitHub](https://github.com/arihantraidani)

---

## 📄 License

MIT License

---

