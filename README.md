# Pattern Mining for Disease Analysis and Diagnosis

## SC4020 Data Analytics & Mining — Project Report 2 Nanyang Technological University, Group 44
---

## Overview

This project applies pattern mining techniques to biomedical datasets to uncover clinically meaningful patterns for disease analysis and diagnosis. It is structured into three tasks, each targeting a different aspect of medical data mining.

---

## Tasks

### Task 1 — Symptom Co-occurrence Pattern Mining (Apriori)

Implements the **Apriori algorithm** from scratch with an adaptive minimum support threshold to identify frequent symptom co-occurrence patterns across 41 diseases. Rather than using a single fixed threshold, minimum support is dynamically adjusted based on the number of unique symptoms per disease, allowing for meaningful pattern discovery across both simple and complex conditions.

**Key highlights:**
- Custom data standardization and synonym mapping for noisy symptom data
- Binary transaction model (one-hot encoding) for symptom presence
- Per-disease analysis with adaptive `min_sup` heuristic
- Identification of high-support symptom combinations (e.g., `{polyuria, increased_appetite}` → Diabetes, support = 1.00)

### Task 2 — Sequential Pattern Mining for Breast Cancer Classification (GSP)

Applies **Generalized Sequential Pattern (GSP)** mining to the Breast Cancer Wisconsin dataset to distinguish malignant from benign cases. Continuous features are transformed into ranked categorical sequences representing each patient's most anomalous features.

**Key highlights:**
- Three discretization strategies compared: Quantile, Uniform, and K-Means
- Feature sequences constructed by ranking absolute Z-scores and selecting the top 5 most deviant features per patient
- Separate GSP mining on malignant (212 sequences) vs. benign (357 sequences) databases
- Sensitivity analysis across discretization strategies to assess pattern stability

### Task 3 — RAG-Based Medical Chatbot

Develops a **Retrieval-Augmented Generation (RAG) medical chatbot** that integrates the symptom patterns discovered in Task 1 with a large language model (LLM). Users can report their symptoms in natural language and receive interpretable disease predictions grounded in the mined patterns.

**Key highlights:**
- RAG pipeline built on top of discovered symptom pattern knowledge base
- Natural language symptom input → disease prediction
- Interpretable outputs linked back to pattern evidence

---

## Repository Structure

```
├── Group44_Source_Code2/
│   ├── Task1.ipynb         # Apriori symptom co-occurrence mining
│   ├── Task2.ipynb         # GSP sequential pattern mining (Breast Cancer)
│   └── Task3.ipynb         # RAG-based medical chatbot
├── Group44_Review_Report2.pdf
├── Group44_Contribution_Summary2.pdf
├── Group44_Video_Link2.pdf
└── README.md
```

---

## Datasets

- **Task 1:** Disease-symptom dataset with 120 patient records per disease across 41 disease classes
- **Task 2:** [Breast Cancer Wisconsin (Diagnostic) Dataset](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)) — 569 samples, 30 continuous features

---

## Requirements

```bash
pip install pandas numpy scikit-learn scipy jupyter
```

Additional packages used in Task 3 (RAG pipeline) may include LLM-related libraries — refer to `Task3.ipynb` for specifics.

---

## Getting Started

1. Clone this repository
2. Install the required dependencies
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Open the notebooks in `Group44_Source_Code2/` and run them in order (Task1 → Task2 → Task3)

---

## Report & Demo

- Full project report: `Group44_Review_Report2.pdf`
- Video demonstration: see `Group44_Video_Link2.pdf` for the link
