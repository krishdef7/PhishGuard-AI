# 🛡️ PhishGuard: AI-Powered Phishing URL Detection

PhishGuard is a machine learning project that detects **phishing websites and malicious URLs** using lexical, domain-based, and statistical features.  
The system is designed to help protect users and organizations against cyberattacks by identifying suspicious links with high accuracy.  

---

## 🚀 Features
- 🔎 **End-to-End ML Pipeline** – preprocessing, feature extraction, training, and prediction  
- 🧠 **Multiple Models Tested** – Random Forest, Gradient Boosting, XGBoost  
- 🛠️ **Feature Engineering** – lexical patterns, domain details, character frequency, entropy  
- 📊 **Performance Metrics** – confusion matrix, ROC-AUC, precision/recall curves  
- ⚡ **Deployment Ready** – modular codebase, can be extended to APIs or browser plugins  

---

## 🏗️ Tech Stack
- **Language:** Python  
- **Libraries:** Scikit-learn, Pandas, NumPy, Matplotlib, XGBoost  
- **Tools:** Jupyter Notebook, Flask/FastAPI (optional for deployment)  

---

## 📂 Project Structure
PhishGuard/
-│── DataFiles/ # Raw and processed datasets
-│── Notebooks/ # Jupyter experiments & EDA
-│── models/ # Saved trained models
-│── app.py # Optional API for predictions
-│── requirements.txt # Python dependencies
-│── README.md # Project documentation


---

## ⚙️ Installation & Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/PhishGuard.git
   cd PhishGuard


Create a virtual environment & install dependencies:

pip install -r requirements.txt


(Optional) Run the training script:

python train.py


(Optional) Start the API for real-time predictions:

python app.py

📊 Results

Accuracy: ~95% on test dataset

AUC-ROC: 0.97

F1-Score: Balanced across classes

Works robustly even with imbalanced phishing datasets (handled using oversampling + class weighting).
