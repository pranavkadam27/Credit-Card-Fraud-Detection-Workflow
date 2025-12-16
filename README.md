# Credit Card Fraud Detection – End-to-End Workflow

**Team Members:**  
- Ashmit Aggarwal (2023152)
- Dhruv Aggarwal (2023197)
- Kaavay Gupta (2023264)
- Pranav Prakash Kadam (2023382)
- Savar Bhasin (2023497)
- Shubh Sharma (2023515)

---

## Project Overview
This project implements an **end-to-end fraud detection workflow** on a large-scale financial dataset. The goal is to **identify fraudulent transactions efficiently** while optimizing training performance.

**Highlights:**
- Dataset: 550,000+ anonymized transactions with 28 features (`V1`–`V28`) and a binary class label.  
- Techniques: Random Forests, Stratified Sampling, Random Projection (JL Transform), Hypothesis Testing, Big-O Complexity Analysis.  
- Achieved **99.92% accuracy** and **0.999 F1-score** on the full dataset.  

---

## Repository Structure

credit-card-fraud-detection/
│
├── main.ipynb # Jupyter Notebook with full workflow
├── README.md # Project documentation
├── requirements.txt # Python dependencies
└──data/ # Dataset or sample subset



---

## Workflow

1. **Data Preprocessing**  
   - Scaled features using **RobustScaler** to handle outliers.  
   - Dataset contained no missing values; no imputation required.  

2. **Exploratory Data Analysis (EDA)**  
   - Investigated distributions and class balance.  
   - Identified top fraud-correlated features: `V12`, `V14`, `V10`, `V3`, `V4`, `V11`.

3. **Statistical Validation**  
   - **Chi-Square Test**, **Z-Test**, **F-Test**, and **Correlation Analysis** to confirm feature significance.  

4. **Model Training & Optimization**  
   - Baseline: Random Forest Classifier on full dataset.  
   - **Stratified Sampling** preserved class ratios.  
   - **Random Projection (JL Transform)** reduced feature dimensions (30 → 15).  
   - Combined approach achieved **~10× faster training** with minimal accuracy loss.  

5. **Evaluation & Complexity Analysis**  
   - Metrics: Accuracy, F1-score, Precision, Recall.  
   - Training complexity reduced from `O(n × m × k × log n)` → `O(s × d × k × log s)`.  

---

## Key Techniques & Libraries
- **Python Libraries:** `numpy`, `pandas`, `scikit-learn`, `matplotlib`, `seaborn`  
- **ML Techniques:** Random Forests, Stratified Sampling, Random Projection (JL Transform)  
- **Statistics:** Hypothesis Testing, Correlation Analysis  
- **Optimization:** Dimensionality reduction, sample size reduction for faster training  

---

## Results
| Approach               | Accuracy | Training Time | Notes |
|------------------------|---------|---------------|-------|
| Baseline (Full Data)   | 99.92%  | 61.49s        | Full dataset, no scaling |
| Random Sampling (20%)  | 99.78%  | 8.41s         | 7.31× speedup |
| Random Projection (15D) | 98.12% | 40.29s       | 1.53× speedup |
| Combined Approach       | 97.81% | 6.16s         | 9.98× speedup, high efficiency |

---

## How to Run
1. **Clone the repository:**

   - git clone https://github.com/pranavkadam27/Credit-Card-Fraud-Detection-Workflow.git


2. **Install dependencies:**

   - pip install -r requirements.txt


3. **Download the dataset (Credit Card Fraud Detection 2023) from Kaggle:**

   - Kaggle Dataset Link: https://www.kaggle.com/datasets/nelgiriyewithana/credit-card-fraud-detection-dataset-2023
   - Save the CSV file into same directory as main.ipynb

4. **Open and run the notebook:**

   - jupyter notebook main.ipynb
