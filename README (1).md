# 🛡️ PhishGuard: AI-Powered Phishing URL Detection  

PhishGuard is a machine learning project that detects **phishing websites and malicious URLs** using features extracted from the URL itself.  
The goal is to improve online safety by identifying suspicious links before they can cause harm.  

---

## ✨ Project Highlights
- Built an **end-to-end ML pipeline** for phishing detection  
- Implemented **feature engineering** (URL length, special characters, entropy, keywords)  
- Trained multiple models: Random Forest, Gradient Boosting, XGBoost  
- Achieved **~95% accuracy** on test data  
- Results evaluated with confusion matrix, F1-score, and ROC-AUC  

---

## 📂 Project Structure
```
PhishGuard/
│── DataFiles/        # Datasets used for training/testing
│── Notebooks/        # Jupyter experiments & analysis
│── models/           # Saved trained models
│── src/phishguard/   # Feature extraction & ML pipeline
│── train.py          # Script to train the model
│── predict.py        # Script to run predictions
│── app.py            # (Optional) API for predictions
│── requirements.txt  # Dependencies
│── README.md         # Project documentation
```

---

## 🚀 How It Works
1. Extracts features from each URL (length, entropy, presence of symbols, keywords, etc.)  
2. Trains a machine learning classifier to distinguish between **benign** and **phishing** URLs  
3. Evaluates performance on test data and saves the model for predictions  

---

## 📊 Results
- Accuracy: ~95%  
- F1-score: 0.94  
- ROC-AUC: 0.97  

---

## 🔮 Future Work
- Experiment with **deep learning models** (LSTM/Transformers for URL embeddings)  
- Build a **browser extension** for real-time phishing detection  
- Deploy with a simple web interface  

---
