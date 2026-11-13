
# 🌐 Network Protocol Classification Using Machine Learning

### An Exploratory Data Analysis and Supervised Machine Learning Project

**Technologies:** Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

**Project Status:** Completed

---

## 1. Project Overview

Network communication involves the exchange of data packets between devices. Each packet contains information such as source, destination, protocol, length, and timestamp.

This project uses supervised Machine Learning techniques to classify network packets into their corresponding protocol categories.

The project follows an end-to-end Machine Learning workflow, including dataset preparation, data cleaning, Exploratory Data Analysis (EDA), feature engineering, model training, and performance evaluation.

Four classification algorithms were implemented:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Random Forest

The Decision Tree achieved the highest testing accuracy of **99.92%**.

## 2. Project Objectives

- Prepare and repair the network packet dataset.
- Perform data cleaning and preprocessing.
- Analyze protocol distribution and packet lengths.
- Extract features from packet timestamps.
- Train multiple Machine Learning models.
- Compare model performance.
- Evaluate predictions using a confusion matrix.
- Identify important features.
- Save the trained model.

## 3. Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Pandas | Data processing |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Machine Learning |
| Joblib | Model saving |
| Google Colab | Development environment |

## 4. Project Structure

```text
Network-Protocol-Classification/
│
├── ML_Project_1.ipynb
├── dataset/
├── models/
├── README.md
└── requirements.txt
```

## 5. Dataset Description

Dataset Name: `KT_GameBox_Merged.csv`

The dataset contains network packet information.

| Column | Description |
|---|---|
| No. | Packet number |
| Time | Packet timestamp |
| Source | Source IP address |
| Destination | Destination IP address |
| Protocol | Network protocol |
| Length | Packet length |
| Info | Additional information |

### Dataset Summary

| Metric | Value |
|---|---:|
| Original Rows | 114,338 |
| Valid Records | 114,337 |
| Columns | 7 |
| Duplicate Records | 0 |
| Protocol Categories | 7 |

### Protocol Distribution

| Protocol | Count | Percentage |
|---|---:|---:|
| UDP | 101,230 | 88.54% |
| TCP | 12,961 | 11.34% |
| TLSv1 | 81 | 0.07% |
| TLSv1.3 | 42 | 0.04% |
| TLSv1.2 | 12 | 0.01% |
| DNS | 10 | 0.01% |
| FMTP | 1 | 0.00% |

## 6. Project Workflow

### Step 1: Dataset Repair
- Read the original CSV file.
- Separate incorrectly merged columns.
- Identify blank records and repeated headers.
- Generate a corrected dataset.

### Step 2: Data Inspection
- Check dataset dimensions.
- Examine column names and data types.
- Identify missing values.
- Check duplicate records.

### Step 3: Data Cleaning
- Convert columns into appropriate data types.
- Handle missing and invalid values.
- Prepare the cleaned dataset.

### Step 4: Exploratory Data Analysis
- Analyze protocol distribution.
- Calculate packet length statistics.
- Create bar charts and histograms.

### Step 5: Feature Engineering

Extracted three features from timestamps:

- Hour
- Minute
- Second

Combined these with packet length.

### Step 6: Feature Selection

Selected features:

- Length
- Hour
- Minute
- Second

Target variable: `Protocol`

### Step 7: Label Encoding

Used Scikit-learn LabelEncoder to convert protocol names into numerical labels.

### Step 8: Train-Test Split

| Dataset | Percentage | Records |
|---|---:|---:|
| Training | 80% | 80,000 |
| Testing | 20% | 20,000 |

Used stratified sampling and random state 42.

FMTP was excluded from model training because it contained only one record.

### Step 9: Feature Scaling

StandardScaler was applied to Logistic Regression and KNN.

### Step 10: Model Training

Implemented four classification algorithms:

1. Logistic Regression
2. K-Nearest Neighbors
3. Decision Tree
4. Random Forest

## 7. Model Performance

| Rank | Algorithm | Accuracy |
|---|---|---:|
| 1 | Decision Tree | **99.92%** |
| 2 | Random Forest | 99.88% |
| 3 | KNN | 99.54% |
| 4 | Logistic Regression | 89.83% |

### Evaluation Metrics

| Metric | Decision Tree |
|---|---:|
| Testing Accuracy | 99.92% |
| Balanced Accuracy | 59.22% |
| Macro F1-score | 0.57 |
| Weighted F1-score | Approximately 1.00 |

**Observation:** The dataset is highly imbalanced because UDP represents approximately 88.54% of all records. Therefore, accuracy alone cannot describe the model's performance across all protocol classes.

## 8. Feature Importance

| Feature | Importance |
|---|---:|
| Length | 99.573% |
| Minute | 0.302% |
| Second | 0.125% |
| Hour | 0.000% |

Packet Length was the most influential feature in the Decision Tree model.

## 9. Prediction Demonstration

| Attribute | Value |
|---|---|
| Packet Length | 40 bytes |
| Hour | 11 |
| Minute | 15 |
| Second | 16 |
| Actual Protocol | TCP |
| Predicted Protocol | TCP |
| Result | Correct |

## 10. Saving the Trained Model

The Decision Tree model and Label Encoder were saved using Joblib.

```python
import joblib

joblib.dump(
    decision_tree_model,
    "best_decision_tree_model.pkl"
)

joblib.dump(
    label_encoder,
    "protocol_label_encoder.pkl"
)
```

## 11. How to Run the Project

### Google Colab

1. Open Google Colab.
2. Upload `ML_Project_1.ipynb`.
3. Upload the original dataset.
4. Check the file paths.
5. Run all notebook cells.

### Local Environment

Clone the repository:

```bash
git clone https://github.com/your-username/Network-Protocol-Classification.git
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

## 12. Requirements

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
joblib
jupyter
```

## 13. Limitations and Future Improvements

1. Handle class imbalance using suitable techniques.
2. Collect more examples of rare protocols.
3. Explore additional packet-level features.
4. Improve model validation using independent datasets.
5. Perform hyperparameter tuning.
6. Improve prediction performance for minority classes.
7. Develop a complete prediction pipeline.
8. Test the model on external network traffic datasets.

## 14. Key Learnings

- Python programming
- Data preprocessing
- CSV data handling
- Exploratory Data Analysis
- Data visualization
- Feature engineering
- Label encoding
- Feature scaling
- Machine Learning model training
- Model evaluation
- Confusion matrix analysis
- Feature importance
- Model saving using Joblib

## 15. Conclusion

This project demonstrates an end-to-end Machine Learning workflow for network protocol classification.

Four classification algorithms were implemented and compared. The Decision Tree achieved the highest testing accuracy of **99.92%**.

The project provided practical experience in data preprocessing, exploratory data analysis, feature engineering, supervised Machine Learning, model evaluation, and model saving.

---

### Built as a Machine Learning Project

*Learning by exploring data, developing models, and evaluating results.*
