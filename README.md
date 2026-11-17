# LPKIA Scholarship Rule Engine

A Decision Tree-based scholarship eligibility evaluation system that transforms machine learning predictions into transparent IF–THEN rules. The application helps evaluate scholarship applicants individually or in batches through CSV files, with interactive decision tree visualization and rule-based explanations.

**Live Demo:** [LPKIA Scholarship Rule Engine](https://nurkalamabdurrahman.github.io/lpkia-scholarship-rule-engine/)

## Overview

LPKIA Scholarship Rule Engine is a lightweight decision support application designed to demonstrate how machine learning can support scholarship eligibility evaluation.

The system uses a Decision Tree model to generate production rules that determine applicant eligibility based on several academic, economic, and organizational criteria.

Instead of presenting predictions as unexplained results, the application provides the matching rules and visualizes the decision path to make the evaluation process easier to understand.

## Features

- **Single Applicant Evaluation** — Evaluate an applicant using individual eligibility criteria.
- **CSV Batch Processing** — Evaluate multiple applicants by uploading a CSV file.
- **Eligibility Prediction** — Classify applicants as eligible or not eligible based on extracted Decision Tree rules.
- **Probability Estimation** — Display the estimated probability of eligibility.
- **Decision Tree Visualization** — Explore the decision structure and highlight the matching evaluation path.
- **Production Rules** — Display the IF–THEN conditions used to determine each prediction.
- **CSV Export** — Download batch evaluation results for further analysis.
- **Input Validation** — Validate applicant data before processing.

## Evaluation Criteria

The system evaluates applicants using the following attributes:

| Attribute | Description |
|---|---|
| IPK | Grade Point Average (2.00–4.00) |
| Penghasilan_Ortu | Monthly parental income in million IDR |
| Jumlah_Tanggungan | Number of family dependents (1–5) |
| Keaktifan_Organisasi | Organizational involvement level |

Organizational activity is represented by three categories:

- `0` — Not Active
- `1` — Active
- `2` — Core Committee

## Decision Tree Model

The eligibility rules are generated using a Decision Tree classifier with the following configuration:

| Parameter | Value |
|---|---|
| Algorithm | Decision Tree |
| Splitting Criterion | Entropy |
| Maximum Depth | 4 |
| Minimum Samples per Leaf | 5 |
| Extracted Rules | 13 |

The trained model is converted into IF–THEN production rules and embedded into the interactive web application.

This approach makes the prediction process more interpretable by showing the conditions that lead to each classification.

## Technology Stack

**Frontend**
- HTML5
- CSS3
- JavaScript

**Machine Learning & Data Processing**
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Joblib
- Jupyter Notebook

**Deployment**
- GitHub Pages

## Project Structure

```text
lpkia-scholarship-rule-engine/
│
├── index.html
├── lpkia_decision_tree.ipynb
├── data_beasiswa.csv
├── rules.json
└── README.md
```

`data_beasiswa.csv` and `rules.json` are generated or used during the model training workflow; their availability depends on the local training process.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/nurkalamabdurrahman/lpkia-scholarship-rule-engine.git

cd lpkia-scholarship-rule-engine
```

### 2. Run the Web Application

Open `index.html` directly in your browser.

Alternatively, access the deployed version:

[Open Live Demo](https://nurkalamabdurrahman.github.io/lpkia-scholarship-rule-engine/)

### 3. Run the Machine Learning Notebook

Install the required Python dependencies:

```bash
pip install pandas numpy scikit-learn matplotlib joblib jupyter
```

Launch Jupyter Notebook:

```bash
jupyter notebook lpkia_decision_tree.ipynb
```

Provide a `data_beasiswa.csv` file in the same directory with the following required columns:

```text
IPK
Penghasilan_Ortu
Jumlah_Tanggungan
Keaktifan_Organisasi
Layak
```

The `Layak` target column uses:
- `1` — Eligible
- `0` — Not Eligible

If the dataset is unavailable, the notebook uses synthetic data for demonstration purposes.

### 4. Update the Decision Rules

After training the model, the notebook exports the extracted rules into `rules.json`.

To update the web application, copy the generated rules into the `const D` configuration in `index.html`.

## CSV Input Format

The application supports batch evaluation using CSV files.

Example:

```csv
Nama,IPK,Penghasilan_Ortu,Jumlah_Tanggungan,Keaktifan_Organisasi
Ayu,3.6,3.0,4,2
Bagas,2.4,12.0,1,0
Citra,3.1,6.0,3,1
Dimas,3.8,10.5,2,2
```

The `Nama` column is optional, while the four evaluation attributes are required.

## Project Purpose

This project explores the application of interpretable machine learning and rule-based decision systems in scholarship eligibility evaluation.

It demonstrates how a trained Decision Tree model can be translated into understandable decision rules, helping users examine the logic behind eligibility predictions.

**Note:** This application is a decision support prototype. Its predictions should not be treated as final scholarship award decisions. Actual scholarship selection requires validated institutional policies, reliable applicant data, and authorized human review.

## Author

**Nurkalam Abdurrahman**

Full-Stack Developer | Indonesia

- GitHub: [@NurkalamAbdurahman](https://github.com/NurkalamAbdurahman)
- LinkedIn: [Nurkalam Abdurrahman](https://linkedin.com/in/nurkalam-abdurrahman)

---

<p align="center">
  <i>Making decision systems more transparent and understandable.</i>
</p>
