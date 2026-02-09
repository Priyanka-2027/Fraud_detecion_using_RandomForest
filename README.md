# 💳 Financial Fraud Detection System

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.95.0-009688)](https://fastapi.tiangolo.com/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.22.0-FF4B4B)](https://streamlit.io/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.2.2-F7931E)](https://scikit-learn.org/stable/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A real-time financial fraud detection system that uses machine learning to identify potentially fraudulent transactions. The system features a FastAPI backend and a Streamlit-based web interface for easy interaction.

## 🌟 Features

- **Real-time Fraud Detection**: Instant prediction of fraudulent transactions.
- **Interactive Web Interface**: User-friendly dashboard for transaction analysis.
- **Machine Learning Model**: Random Forest Classifier trained on financial transaction data.
- **RESTful API**: Easy integration with other systems
- **Comprehensive Logging**: Detailed logs for monitoring and debugging

## 📊 Dataset

The model is trained on a synthetic financial transactions dataset containing the following features:

| Feature | Description | Type |
|---------|-------------|------|
| step | Unit of time (1 step = 1 hour) | Integer |
| type | Type of transaction (PAYMENT, TRANSFER, CASH_OUT, CASH_IN, DEBIT) | Categorical |
| amount | Transaction amount | Float |
| oldbalanceOrg | Initial balance before transaction | Float |
| newbalanceOrig | New balance after transaction | Float |
| oldbalanceDest | Recipient's balance before transaction | Float |
| newbalanceDest | Recipient's balance after transaction | Float |
| isFraud | Whether the transaction is fraudulent (0/1) | Binary |

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/finance_fraud.git
   cd finance_fraud
   ```

2. Create and activate a virtual environment:
   ```bash
   # Windows
   python -m venv venv
   .\venv\Scripts\activate
   
   # Linux/MacOS
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Application

1. **Start the FastAPI backend** (in a new terminal):
   ```bash
   cd api
   uvicorn app:app --reload --port 8001
   ```
   The API will be available at: `http://localhost:8001`
   - API Documentation: `http://localhost:8001/docs`
   - Alternative Docs: `http://localhost:8001/redoc`

2. **Start the Streamlit UI** (in a new terminal):
   ```bash
   streamlit run ui.py
   ```
   The web interface will open automatically in your default browser at: `http://localhost:8501`

## 🛠️ Project Structure

```
finance_fraud/
├── api/
│   └── app.py                  # FastAPI backend server
├── models/
│   ├── fraud_model_new.pkl     # Trained model
│   └── feature_names_new.pkl   # Feature names for the model
├── notebooks/
│   └── fraud_detection_eda.ipynb  # Jupyter notebook for EDA and model training
├── reports/
│   └── figures/                # Saved visualizations
├── .gitignore                  # Git ignore file
├── README.md                   # This file
├── dataset_fraud.csv           # Dataset
├── requirements.txt            # Python dependencies
└── ui.py                       # Streamlit web interface
```

## 📈 Model Performance

The Random Forest Classifier was chosen for its ability to handle imbalanced data and provide feature importance. Key metrics:

- **Accuracy**: 99.8%
- **Precision**: 0.98
- **Recall**: 0.90
- **F1-Score**: 0.94
- **ROC-AUC**: 0.99

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request


## 🙏 Acknowledgments

- Dataset sourced from [Synthetic Financial Datasets For Fraud Detection](https://www.kaggle.com/datasets/ealaxi/paysim1)
- Inspired by real-world financial fraud detection systems
- Built with ❤️ using Python, FastAPI, and Streamlit

## 🔧 Tech Stack

- **ML**: scikit-learn, pandas, numpy, matplotlib, seaborn, imbalanced-learn
- **Backend**: FastAPI, uvicorn, joblib
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Notebook**: Jupyter Lab

## 📊 API Endpoints

### POST `/predict`

**Request Body:**
```json
{
  "step": 1,
  "type": "TRANSFER",
  "amount": 181.0,
  "oldbalanceOrg": 181.0,
  "newbalanceOrig": 0.0,
  "oldbalanceDest": 0.0,
  "newbalanceDest": 0.0
}
```

**Response:**
```json
{
  "is_fraud": 1,
  "fraud_probability": 0.87,
  "risk_level": "HIGH",
  "message": "⚠️ FRAUD DETECTED - High Risk Transaction"
}
```

## 🎓 Learning Outcomes

1. ✅ Exploratory Data Analysis (EDA)
2. ✅ Handling imbalanced datasets
3. ✅ Feature engineering
4. ✅ Model training and evaluation
5. ✅ Model serialization
6. ✅ Building REST APIs
7. ✅ Frontend-backend integration
8. ✅ Real-time ML predictions.

## Output Screenshots
<img width="1867" height="1089" alt="Screenshot 2025-12-03 233727" src="https://github.com/user-attachments/assets/e4c8297d-1584-40f1-b099-63991aebaa7a" />
<img width="1690" height="975" alt="Screenshot 2025-12-03 233842" src="https://github.com/user-attachments/assets/787b638d-86b1-4536-86f4-fdb1d39f49bd" />
<img width="1690" height="969" alt="Screenshot 2025-12-03 233901" src="https://github.com/user-attachments/assets/3808dbcf-c5f7-4fdb-ae89-167d1b0172fb" />
<img width="1615" height="1005" alt="Screenshot 2025-12-03 234056" src="https://github.com/user-attachments/assets/c40e435e-fe65-486f-a57c-5a73bd1cf4ce" />

**Built with ❤️ for ML Learning**
