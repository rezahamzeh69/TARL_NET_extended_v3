# TARL-Net

> **Threat-Aware Adaptive Representation Learning Network for Intelligent Intrusion Detection**

A research-oriented implementation of **TARL-Net**, a hybrid deep learning framework for intelligent intrusion detection, zero-day attack recognition, self-supervised representation learning, open-set recognition, continual learning, and explainable cyber threat intelligence.

---

## Overview

TARL-Net is a unified deep learning framework designed to address several major limitations of modern Intrusion Detection Systems (IDSs).

Unlike conventional IDS models that rely on fully supervised closed-set learning, TARL-Net integrates multiple state-of-the-art AI techniques into a single end-to-end architecture capable of:

- Detecting known attacks
- Identifying previously unseen (Zero-Day) attacks
- Learning from unlabeled network traffic
- Adapting to concept drift
- Producing explainable security decisions
- Supporting early attack prediction

The framework was developed as part of a PhD research project in Artificial Intelligence for Cybersecurity.

---

# Key Features

✔ Hybrid Transformer–BiLSTM Architecture

✔ Threat-Aware Adaptive Vector Fusion

✔ Self-Supervised Representation Learning

✔ Open-Set Recognition (Zero-Day Detection)

✔ Explainable AI (Attention Rollout + Integrated Gradients)

✔ Confidence Calibration

✔ Continual Learning (Replay + EWC)

✔ Early Threat Prediction

✔ Multi-Seed Evaluation

✔ Cross-Dataset Zero-Shot Transfer

✔ Robust Experimental Protocol

---

# Notebook

This repository currently contains the complete implementation inside:

```
TARL_NET_extended_v3.ipynb
```

The notebook includes the entire research pipeline from data preprocessing to evaluation.

---

# Research Pipeline

```
Raw Network Traffic
        │
        ▼
Data Preprocessing
        │
        ▼
Feature Engineering
        │
        ▼
Self-Supervised Pretraining
        │
        ▼
Hybrid Encoder

 ┌─────────────────┐
 │  Transformer    │
 └─────────────────┘

        +

 ┌─────────────────┐
 │     BiLSTM      │
 └─────────────────┘

        │
        ▼

Threat-Aware Adaptive Fusion

        │
        ▼

Open-Set Recognition

        │
        ▼

Threat Classification

        │
        ▼

Explainability

        │
        ▼

Threat Intelligence Report
```

---

# Main Components

## Hybrid Feature Encoder

The proposed architecture combines

- Transformer
- Bidirectional LSTM

to simultaneously model

- long-range dependencies
- sequential temporal behavior
- contextual traffic relationships

---

## Threat-Aware Adaptive Fusion

Instead of static feature concatenation, TARL-Net dynamically learns the contribution of each representation using a threat-aware adaptive vector gate.

---

## Self-Supervised Learning

To reduce dependency on expensive labeled datasets, the model performs

- Masked Traffic Modeling
- Contrastive Learning

before supervised fine-tuning.

---

## Open-Set Recognition

Unknown attacks are identified using a class-conditional Deep SVDD framework capable of distinguishing

- Known attacks
- Unknown attacks
- Benign traffic

without forcing all samples into predefined classes.

---

## Explainable AI

The framework provides

- Attention Rollout
- Integrated Gradients
- Confidence Calibration

to improve operational trust.

---

## Continual Learning

Replay Memory and Elastic Weight Consolidation (EWC) are employed to reduce catastrophic forgetting under concept drift.

---

# Experimental Additions (v3)

The current notebook includes the final reviewer-requested additions:

- Independent-dataset Zero-Shot Transfer
- Multi-seed Ablation Analysis
- MCC
- Cohen's Kappa
- Balanced Accuracy
- Continual Learning Evaluation
- Wall-clock Runtime Analysis
- Multi-horizon Prediction
- Thesis Figure Export Utilities

---

# Repository Structure

```
.
├── CITATION.cff
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE.md
├── README.md
├── SECURITY.md
└── TARL_NET_extended_v3.ipynb
```


# Requirements

Python 3.10+

Recommended libraries:

```
torch
numpy
pandas
scikit-learn
matplotlib
scipy
shap
captum
jupyter
```

---

# Installation

Clone the repository

```bash
git clone https://github.com/rezahamzeh69/TARL-Net-ZeroDay-IDS.git
```

Enter the project

```bash
cd TARL_NET_extended_v3
```

Install dependencies

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook

```bash
jupyter notebook
```

Open

```
TARL_NET_extended_v3.ipynb
```

---

# Running

Execute notebook cells sequentially.

The final experiment can be launched using

```python
main_full_v3(ConfigX(seeds=(1337,)))
```

---

# Evaluation Metrics

The notebook reports

- Accuracy
- Precision
- Recall
- F1-score
- Macro F1
- AUROC
- MCC
- Cohen's κ
- Balanced Accuracy
- False Positive Rate
- Open-Set AUROC
- Early Warning Score
- Runtime
- Memory Usage

---

# Dataset

The implementation is designed for benchmark intrusion detection datasets including

- UNSW-NB15

and supports cross-dataset transfer evaluation.

---

# Research Contributions

The proposed framework introduces

- Threat-aware adaptive representation fusion
- Self-supervised traffic representation learning
- Open-set Zero-Day detection
- Explainable cyber threat intelligence
- Continual learning under concept drift
- Early attack prediction
- Robust evaluation protocol

within a unified architecture.

---

# Citation

If you use this repository in your research, please cite:

```bibtex
@misc{hamzeh2026tarlnet,
  title={TARL-Net: Threat-Aware Adaptive Representation Learning Network},
  author={Reza Hamzeh},
  year={2026},
  note={Research implementation}
}
```

---

# License

This project is intended for academic and research purposes.

---

# Acknowledgment

This repository accompanies doctoral research on intelligent cyber threat detection, trustworthy artificial intelligence, and next-generation intrusion detection systems.
