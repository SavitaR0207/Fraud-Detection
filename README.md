# Vesta E-Commerce Fraud Detection Project Summary

## Introduction
This project aims to enhance fraud detection systems within the e-commerce sector by analyzing a substantial dataset of real-world transactions in partnership with IEEE-CIS and Vesta Corporation.

## Dataset
- **Size**: 590,540 transactions with 434 features
- **Key Features**: Includes transaction amount, transaction time, card details, address, distance, email domains, and various anonymized attributes.

## Exploratory Data Analysis
- **Transaction Amounts**: A log transformation revealed distinct patterns between fraudulent and legitimate transactions.
- **Timing Patterns**: Fraudulent transactions were often found to occur at unusual hours.
- **Feature Importance**: PCA was utilized to reduce multicollinearity, identifying critical features such as 'TransactionAmt' and 'TransactionDT'.

## Challenges
- **Imbalanced Data**: The dataset displayed a significant imbalance between fraudulent and non-fraudulent transactions, complicating effective model training. Techniques like SMOTE were not feasible due to the nature of many anonymous features. Thus, we focused on comprehensive feature selection and models designed to address imbalance.
- **Feature Selection**: Selecting the most pertinent features from a vast pool of 434 required thorough visual analysis and dimensionality reduction techniques like PCA and Random Forest feature importance.

## Model Selection
- **Objective**: The aim was to balance recall and precision to reduce false positives while maximizing fraud detection.
- **Hyperparameter Tuning**: Grid search was performed for Random Forest, Logistic Regression, and XGBoost.
  - **Random Forest**: ROC-AUC of 0.89
  - **Logistic Regression**: ROC-AUC of 0.51
  - **XGBoost**: ROC-AUC of 0.88

## Precision-Recall Analysis
- **Threshold Experimentation**: XGBoost demonstrated greater stability and performance across varying thresholds, which led to its selection as the final model.

## Final Model Choice
The XGBoost model was selected for its impressive performance and well-balanced precision-recall metrics, achieving an F1-score of 0.76, with nearly equal precision and recall scores for both classes, and an overall accuracy of 81%.

## Further Work
- **Model Integration**: Investigate ensemble methods that combine Random Forest and XGBoost.
- **Real-Time Deployment**: Assess the model’s effectiveness in a live environment for real-time fraud detection.

This project significantly improves fraud detection accuracy, providing robust protection while minimizing disruptions for genuine users.

---

## Getting Started

### Prerequisites
Make sure you have the following prerequisites installed and configured:
- **Python Version**: Python 3.10.12 (recommended: 3.8 or higher)
- **Libraries and Dependencies**: Install all necessary libraries listed in `requirements.txt`.
- **Google Account**: Required for Google Colab.
- **Local or Cloud Environment**: Capable of running Jupyter notebooks if not using Google Colab.

### Installation
Follow these steps to establish the project environment:
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```
2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Notebook

#### Google Colab
1. Open Google Colab.
2. Click on **File > Open notebook > GitHub tab** and paste the URL of your notebook.
3. Alternatively, use **File > Upload notebook** to upload from your local machine.
4. Follow the instructions in the notebook to mount Google Drive if necessary.

#### Local Jupyter Installation
1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Navigate to the notebook file in the Jupyter interface and open it.
3. Run the cells sequentially to replicate the analysis.

### Setting Up the Kaggle API and Downloading the Dataset
To use datasets from Kaggle, configure the Kaggle API as follows:

1. **Create or Log Into Your Kaggle Account**.
2. **API Token Generation**:
   - Navigate to your account settings and click **Create New API Token**. This action downloads `kaggle.json`.
3. **Setup API Token**:
   - Place `kaggle.json` in the `~/.kaggle/` directory for Unix-like systems.

### Explore the Dataset
Visit the [IEEE Fraud Detection Kaggle Competition](https://www.kaggle.com/c/ieee-fraud-detection) page to explore and understand the dataset.

### Dataset Download and Setup
Execute the following commands in your notebook:
```bash
# Create the necessary Kaggle directory
!mkdir ~/.kaggle

# Copy the kaggle.json file into this directory
!cp /your/drive/kaggle.json ~/.kaggle/

# Secure the API token
!chmod 600 ~/.kaggle/kaggle.json

# Download the dataset
!kaggle competitions download -c ieee-fraud-detection

# Unzip the dataset
!unzip /content/ieee-fraud-detection.zip
```


## Acknowledgments
This project draws inspiration from, and acknowledges the datasets and code snippets provided by, the IEEE Computational Intelligence Society, the source of the Kaggle dataset.
