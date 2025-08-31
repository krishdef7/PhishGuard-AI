# 🛡️ PhishGuard: AI-Powered Phishing URL Detection  

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![ML](https://img.shields.io/badge/Machine%20Learning-Scikit--learn%20%7C%20XGBoost-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Status-Active-success)

PhishGuard is a machine learning system that detects **phishing websites and malicious URLs** using lexical, statistical, and domain-based features.  
It is designed to protect users and organizations from cyberattacks by identifying suspicious links with high accuracy.  

---

## 🚀 Features
- 🔎 **End-to-End ML pipeline** (data preprocessing → training → prediction)  
- 🧠 **Models tested**: Random Forest, Gradient Boosting, XGBoost  
- 🛠️ **Feature Engineering**: URL length, entropy, subdomains, character counts, phishing keywords  
- 📊 **Evaluation Metrics**: Accuracy, Precision/Recall, F1-score, ROC-AUC  
- ⚡ **Deployment Ready**: Includes a **FastAPI** service for real-time predictions  

---

## 📂 Project Structure
```
PhishGuard/
│── DataFiles/        # Raw and processed datasets
│── Notebooks/        # Jupyter experiments & EDA
│── models/           # Saved trained models
│── src/phishguard/   # Feature extraction & ML pipeline
│── train.py          # Training script
│── predict.py        # CLI prediction script
│── app.py            # FastAPI app for real-time predictions
│── requirements.txt  # Python dependencies
│── README.md         # Project documentation
```

---

## ⚙️ Installation & Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/PhishGuard.git
   cd PhishGuard
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## 🏋️ Training the Model
Your dataset should be in CSV format inside `DataFiles/urldata.csv` with at least two columns:  
- **url** → The website link  
- **label** → 0 (benign), 1 (phishing)  

Run training:
```bash
python train.py --data DataFiles/urldata.csv
```

This saves the trained model in:
```
models/phishguard_xgb.joblib
```

---

## 🔮 Making Predictions

**Single URL**
```bash
python predict.py --url "https://secure-login.update-account.xyz"
```

**Batch Prediction from CSV**
```bash
python predict.py --file DataFiles/urls_to_score.csv
```

Predictions are saved to `predictions.csv`.

---

## 🌐 Running the API

Start FastAPI server:
```bash
uvicorn app:app --reload --port 8080
```

**Single URL Request**
```bash
curl -X POST http://127.0.0.1:8080/predict      -H "Content-Type: application/json"      -d '{"url":"https://secure-login.update-account.xyz"}'
```

**Batch Request**
```bash
curl -X POST http://127.0.0.1:8080/predict_batch      -H "Content-Type: application/json"      -d '{"urls": ["http://example.com","http://bit.ly/free-gift"]}'
```

---

## 📊 Results (Sample)
- **Accuracy**: ~95%  
- **F1-score**: 0.94  
- **ROC-AUC**: 0.97  
- Robust even on imbalanced datasets via oversampling and class weighting.  

---

## 🔮 Future Improvements
- Deep learning (LSTM/Transformers for URL embeddings)  
- Browser extension for real-time phishing alerts  
- Enterprise dashboard integration  

---

## 🤝 Contributing
Contributions are welcome!  
- Fork the repo  
- Create a new branch (`feature-xyz`)  
- Commit your changes  
- Open a Pull Request  

---

## 📜 License
This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.  

---

## 🙌 Acknowledgments
- Open-source phishing URL datasets  
- Scikit-learn & XGBoost communities  
- Cybersecurity research that inspired this work  
