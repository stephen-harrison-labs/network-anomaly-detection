# Network Intrusion Detection System (NIDS) Using Random Forests

This project implements a complete, well-structured machine learning workflow for detecting network intrusions using the **NSL-KDD** dataset.  
It classifies network traffic into five categories:

- Normal  
- DoS  
- Probe  
- Privilege Escalation  
- Access Attacks  

The goal is to provide a clear, realistic, and educational example of how machine learning can be applied to intrusion detection — suitable for learning and portfolio use.

---

## Overview

The notebook walks through an end-to-end ML pipeline, including:

- Loading and preparing the NSL-KDD dataset  
- Encoding categorical features  
- Creating binary & multi-class labels  
- Train/validation/test splits  
- Training a Random Forest classifier  
- Evaluation (accuracy, precision, recall, F1-score)  
- Confusion matrices  
- Feature importance & interpretation  
- Saving/loading models (joblib)  
- Example inference workflow  
- Notes on how ML-based NIDS systems operate in practice  

This project is intended for **learning and experimentation**, not as a production intrusion detection system.

---

## Results

On the unseen test split, the Random Forest achieved:

| Metric | Score |
|--------|--------|
| Accuracy | 99.49% |
| Precision | 99.47% |
| Recall | 99.49% |
| F1-Score | 99.47% |

Performance varies by attack type:  
Normal, DoS, and Probe are the strongest categories, while Privilege Escalation remains challenging due to limited representation in the dataset.

---

## Feature Importance

Top contributing features include:

- `src_bytes` / `dst_bytes`  
- Connection count metrics (`count`, `srv_count`)  
- Service-based ratios  
- Error/flag-based indicators  

A full importance plot and explanation are included in the notebook.

---

## Model Saving & Loading

The trained model is saved as:

network_anomaly_detection_model.joblib


It can be loaded for inference using:

```markdown
```python
model = joblib.load("network_anomaly_detection_model.joblib")
'''

--

## Deployment Notes (Educational)

The notebook includes lightweight examples of:

- Running predictions on new traffic samples  
- A minimal FastAPI endpoint for inference  
- Batch-style log analysis  
- How ML-based detectors can complement SIEM pipelines  

These examples illustrate how a model like this could be integrated into a broader system.

---

## Purpose of This Project

This project was built to:

- Practice ML using a realistic security dataset  
- Learn key concepts in intrusion detection  
- Strengthen preprocessing, evaluation, and interpretation skills  
- Produce a clean, portfolio-ready notebook  
- Form a foundation for future AI security work  

---

## Notes

The NSL-KDD dataset is older and simplified compared to modern traffic,  
but remains a well-known benchmark for:

- teaching  
- research  
- comparing intrusion detection models  

The focus here is **clarity, structure, and applied understanding**, not production-level deployment.


