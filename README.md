# Hybrid Quantum–Classical Fraud Detection

A machine learning project exploring the use of **classical machine learning, deep learning, and quantum machine learning** for credit card fraud detection. The project compares different approaches for identifying fraudulent transactions in a highly imbalanced dataset and investigates the potential of Variational Quantum Classifiers (VQC).

## Overview

Credit card fraud detection is a challenging classification problem because fraudulent transactions represent only a small fraction of all transactions. Traditional models may achieve high accuracy while failing to identify a meaningful proportion of fraudulent cases.

This project evaluates classical and quantum machine learning approaches using a consistent experimental workflow, with emphasis on class imbalance, decision-threshold selection, and evaluation using metrics beyond accuracy.

## Objectives

- Develop classical machine learning baselines for fraud detection.
- Explore neural network-based classification.
- Implement hybrid quantum–classical learning experiments using Variational Quantum Classifiers.
- Compare models using appropriate classification metrics.
- Investigate the effect of feature selection and dimensionality reduction on model performance.
- Evaluate the trade-offs between predictive performance and computational cost.

## Technologies Used

- **Language:** Python
- **Environment:** Google Colab / Jupyter Notebook
- **Data Processing:** NumPy, Pandas
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn, XGBoost, Imbalanced-learn
- **Statistical Analysis:** Statsmodels
- **Deep Learning:** PyTorch
- **Quantum Machine Learning:** Qiskit, Qiskit Machine Learning, Qiskit Algorithms

## Methodology

### 1. Data Preprocessing and Analysis

- Load and inspect the credit card transaction dataset.
- Examine feature relationships and multicollinearity using correlation analysis and Variance Inflation Factor (VIF).
- Split the data into training, validation, and test sets using stratification.
- Prepare the data for classical and quantum model training.

### 2. Classical Machine Learning

Establish baseline performance using classical machine learning algorithms. Model selection and decision-threshold tuning are performed using validation data.

### 3. Deep Learning

Explore neural network-based models to learn patterns that distinguish legitimate transactions from fraudulent ones.

### 4. Quantum Machine Learning

Investigate Variational Quantum Classifiers (VQC) using different feature counts, including 4, 8, 12, and 16 features. Evaluate the impact of feature dimensionality on model performance and computational feasibility.

### 5. Dimensionality Reduction

Explore Principal Component Analysis (PCA) as an optional experiment to reduce feature dimensionality and study its effect on classification.

### 6. Model Evaluation and Comparison

Evaluate model performance using metrics suited to imbalanced classification, including:

- Precision
- Recall
- F1-score
- Average Precision / Precision–Recall analysis
- Confusion matrix

Accuracy is considered alongside these metrics rather than used as the sole measure of performance.

## Project Structure

```text
hybrid-quantum-classical-fraud-detection/
│
├── hybrid_quantum_classical_fraud_detection.ipynb
├── requirements.txt
├── README.md
├── .gitignore
│
└── data/
    └── .gitkeep
```

## Dataset

This project uses a credit card fraud detection dataset containing transaction features and a binary target variable.

- **Target column:** `Class`
- **Class 0:** Legitimate transaction
- **Class 1:** Fraudulent transaction

### Dataset Setup

The dataset is not included in this repository.

1. Obtain the dataset from an authorized source, such as the [Kaggle Credit Card Fraud Detection dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).
2. Create a `data` folder in the project directory.
3. Place the CSV file inside the folder and name it `creditcard.csv`.
4. Ensure the notebook's dataset path points to the correct file.

The `.gitignore` file excludes CSV files inside `data/` to help prevent accidental uploads of large datasets.

## Installation and Setup

### Prerequisites

- Python 3.10 or 3.11 recommended
- Jupyter Notebook, JupyterLab, VS Code, or Google Colab
- Sufficient memory and computational resources for model training

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/hybrid-quantum-classical-fraud-detection.git
cd hybrid-quantum-classical-fraud-detection
```

Replace `YOUR_USERNAME` with your GitHub username.

### 2. Create a Virtual Environment (Optional)

```bash
python3 -m venv .venv
source .venv/bin/activate
```

On Windows, activate the environment with:

```bash
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Run the Notebook

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open `hybrid_quantum_classical_fraud_detection.ipynb`, configure the dataset path, and execute the cells in order.

## Running on Google Colab

Google Colab can be used to run the notebook without configuring a local Python environment.

1. Open the notebook in Google Colab.
2. Upload the dataset or mount Google Drive.
3. Update the dataset path if necessary.
4. Select **Runtime → Change runtime type** and choose a GPU runtime if available and appropriate.
5. Execute the notebook from the beginning.

**Note:** A GPU does not accelerate every experiment. Some scikit-learn algorithms and quantum circuit simulations may run primarily on the CPU. Quantum simulation can be computationally expensive, particularly as circuit size increases.

## Experimental Considerations

- Use the validation set for model selection and threshold tuning.
- Keep the final test set separate from model development.
- Account for class imbalance when interpreting metrics.
- Interpret precision and recall in the context of the chosen decision threshold.
- Quantum experiments may use a smaller, fraud-enriched test subset to make simulation computationally feasible. Metrics from this subset should not be directly compared with metrics from the original full test population without accounting for the difference in class prevalence.
- Record package versions, dataset versions, random seeds, and runtime configuration when reproducing experiments.

## Results

Model performance should be reported after running the notebook. This repository does not claim fixed benchmark scores because results depend on the dataset, configuration, runtime, and experimental settings.

A useful final comparison includes each model's precision, recall, F1-score, average precision, computational requirements, and limitations.

## Future Enhancements

Potential extensions include:

- More extensive hyperparameter optimization.
- Additional classical ensemble models.
- Alternative quantum feature maps and variational circuit architectures.
- Repeated experiments across random seeds.
- Statistical significance testing.
- Training-time and inference-time comparisons.
- Evaluation on additional fraud datasets.
- A lightweight web application for interactive fraud prediction.

## Limitations

- Quantum machine learning simulations can be slow and resource-intensive.
- Results on a sampled test subset may not generalize directly to the full transaction population.
- Performance on a public dataset does not establish readiness for real-world financial deployment.
- Quantum models should be evaluated empirically against strong classical baselines before drawing conclusions about their advantages.

## Disclaimer

This project is intended for educational and research purposes. It is not a production-ready financial fraud detection system and should not be used to make real financial decisions without further validation, security review, and testing.

## License

No license has been specified. Add an appropriate open-source license if you intend to permit reuse or redistribution.

---

**If you find this project useful, consider starring the repository!**
