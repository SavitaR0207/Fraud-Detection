# **Fraud Detection in credit card transactions**

This project seeks to design a foundational fraud detection system to identify suspicious credit card transactions. By employing supervised learning techniques, it establishes a critical framework to address and mitigate the challenges of credit card fraud faced by financial institutions.

## **Table of Contents**

- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)

## **Technologies Used**

- **Python**: Programming language used for development.
- **FastAPI**: Framework for building the API.
- **Scikit-learn**: Machine learning library used for model training.
- **Pandas**: Data manipulation library.
- **NumPy**: Library for numerical operations.
- **Joblib**: Library for model serialisation.

## **Getting Started**

To get a local copy of this project up and running, follow these steps:

### **Installation**

1. Clone the repository:
```bash
   git clone https://github.com/nafisalawalidris/Fraud-Detection-with-Supervised-Learning.git
```

2. Navigate to the project directory:
```bash
cd Fraud-Detection-with-Supervised-Learning
```

3. Create a virtual environment:
```bash
python -m venv fraud_detection_env
```

4. Activate the virtual environment:
- On Windows:
```bash
.\fraud_detection_env\Scripts\activate
```
- On macOS/Linux
```bash
source fraud_detection_env/bin/activate
```

5. Install the required packages:
```bash
pip install -r requirements.txt
```

## **Usage**
1. Run the FastAPI server:
```bash
uvicorn main:app --reload
```
Then open your browser and go to http://localhost:8501.

2. Send a POST request to the /predict endpoint with transaction data in the following format:
```bash
{
    "Time": 123456,
    "V1": 0.0,
    "V2": 1.0,
    ...
    "Amount": 100.00
}
```
3. Receive a response with fraud prediction and probability:
```bash
{
    "fraud_prediction": true,
    "fraud_probability": 0.95
}
```

## **Features**
- Simple and effective fraud detection using supervised learning techniques.
- RESTful API built with FastAPI for easy integration.
- Detailed logging of predictions and transactions.
- Well-structured codebase that allows for easy modifications and enhancements.

## **Contributing**
Contributions are welcome, If you have suggestions for improvements or want to contribute to this project, please fork the repository and create a pull request.
