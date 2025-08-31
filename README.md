# PhishGuard AI – Phishing Website Detection 🔒  

PhishGuard AI is a machine learning project that detects **phishing websites** using **XGBoost**, trained on carefully engineered URL and domain features. The model leverages handcrafted indicators extracted from both **PhishTank** (phishing URLs) and **UNB datasets** (benign URLs).  

---

## 🚀 Features
- **17 handcrafted features** grouped into 3 categories:  
  - **Address Bar features**  
  - **Domain features**  
  - **HTML & JavaScript features**  
- Implements **XGBoost Classifier** for phishing detection.  
- Achieves strong accuracy on both training and testing datasets.  
- Supports easy retraining and extension with new data.  
- Saves trained model (`phishguard_xgb.pkl`) for reuse.  

---

## 📂 Repository Structure
```
PhishGuard/
├── DataFiles/
│   └── urldata.csv          # Dataset with 17 features + label
├── train.py                 # Training script (XGBoost pipeline)
├── predict.py               # Script to classify new URLs
├── models/
│   └── phishguard_xgb.pkl   # Saved trained model
├── requirements.txt         # Python dependencies
└── README.md                # Project documentation
```

---

## ⚙️ Setup & Installation

1. **Clone the repo**
   ```bash
   git clone https://github.com/<your-username>/PhishGuard-AI.git
   cd PhishGuard-AI
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. *(Optional)* If you don’t have `xgboost` installed:
   ```bash
   pip install xgboost
   ```

---

## 🏋️ Training

Run the training script to build the phishing detection model:

```bash
python train.py --data DataFiles/urldata.csv --target label
```

- Loads dataset (`urldata.csv`).  
- Splits into **80% training** and **20% testing**.  
- Trains an **XGBoost Classifier**.  
- Prints classification metrics and saves the trained model in `models/phishguard_xgb.pkl`.  

---

## 🧪 Testing / Inference

Use the saved model to classify new URLs:  

```bash
python predict.py --model models/phishguard_xgb.pkl --input sample_urls.csv
```

- Outputs predicted labels (`0 = benign`, `1 = phishing`) and probabilities.  

---

## 📊 Dataset & Results

- Dataset size: ~10,000 URLs (5,000 phishing + 5,000 legitimate) sourced from:  
  - **PhishTank** (phishing)  
  - **University of New Brunswick (UNB)** dataset (benign)  
- Split: **80% training, 20% testing**.  
- Achieved performance (original project benchmark):  
  - **Train Accuracy**: ~86.7%  
  - **Test Accuracy**: ~85.8%  

*(You should rerun on your own dataset for updated results.)*

---

## 📜 License
This project is open-source and available for research and educational purposes.  

---

📌 *Future Directions*:  
- Add deep learning baselines (LSTM, Transformers on raw URLs).  
- Integrate real-time URL scanning.  
- Deploy as a browser plugin or REST API for live phishing protection.  
