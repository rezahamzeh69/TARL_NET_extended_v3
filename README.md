# TARL-Net: Threat-Aware Transformer–LSTM Network for Open-Set Zero-Day Intrusion Detection and Interpretable Threat Intelligence

<p align="center">
  <img src="https://img.shields.io/badge/python-3.10%2B-blue.svg" alt="Python 3.10+">
  <img src="https://img.shields.io/badge/PyTorch-2.0%2B-ee4c2c.svg" alt="PyTorch">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT">
  <img src="https://img.shields.io/badge/Degree-Ph.D.%20Dissertation-gold.svg" alt="Academic Status">
</p>

The **TARL-Net** framework is an end-to-end, unified architecture for cyber attack detection and forecasting based on deep learning. The core focus of this research is the transition from traditional closed-set systems to a resilient system operating in open-set environments, capable of identifying zero-day attacks with calibrated interpretability and continuous adaptation against concept drift.

---

## 📌 Core Innovations & Key Features

TARL-Net is organized around a primary scientific contribution supported by five foundational components:

1. **Per-Dimension Adaptive Gating Conditioned on Threat Context:** The core innovation dynamically blends global (Transformer) and temporal (BiLSTM) representations on a per-dimension basis, guided by a learnable threat context routing vector.
2. **Semantic-Preserving Self-Supervised Pre-training (SSL):** Masked traffic modeling featuring a progressive strategy and contrastive learning to mitigate extreme dependency on labeled datasets.
3. **Class-Conditional Open-Set Recognition (OSR) Gateway:** Reformulating the Deep SVDD method with hypersphere anti-collapse mechanisms and quantile thresholding to structurally isolate known behaviors from zero-day threats.
4. **Two-Level Operational Trust Layer:** Real-time online interpretability powered by *Attention Rollout* for instant security operations, and offline forensic analysis utilizing *Integrated Gradients*, complemented by temperature calibration (yielding an ECE of 0.0188).
5. **Analyst-in-the-Loop Continual Learning:** Counteracting concept drift by combining an experience replay buffer with Elastic Weight Consolidation (EWC).
6. **Short-Horizon Forecasting & Early Warning:** Enabling early warning score issuance prior to the full execution of multi-stage attack scenarios.

---

## 📊 Evaluation Protocol & Dataset

Experimental evaluations were conducted on the full version of the benchmark **UNSW-NB15** dataset (retaining precise temporal and contextual sequence data). To rigorously evaluate real-world generalization, a strict **Leave-One-Attack-Family-Out (LOAFO)** protocol was executed across 3 distinct random seeds.

### Anti-Data-Leakage Safeguards
* Non-overlapping flow windowing constructed using the `(Host, Service)` key structure.
* All statistical parameters and robust preprocessing scalers were fitted exclusively on the training partition.

---

## 📈 Experimental Results

Summary of operational performance and evaluation metrics derived from multi-seed simulations (reported as Mean ± Standard Deviation):

| Evaluation Metric | Value / Status | Operational & Managerial Implication |
| :--- | :---: | :--- |
| **Closed-Set Accuracy** | 0.9916 | Exceptional precision in identifying conventional network behaviors. |
| **Macro-F1 Score** | 0.4424 | Honest performance reflection under severe class imbalance conditions. |
| **OSR-AUROC (Zero-Day)** | 0.9633 ± 0.0376 | High and stable capability in isolating unknown novel attacks. |
| **Expected Calibration Error (ECE)** | 0.0188 | High reliability regarding the confidence scores output by the model. |
| **Explanation Fidelity (Insertion Metric)** | 0.8479 | Strong alignment between provided XAI explanations and actual model behavior. |
| **Inference Latency** | ~0.013 ms | Extremely lightweight, suitable for line-rate real-time deployment. |
| **Memory Overhead** | ~97 MB | Very low Total Cost of Ownership (TCO) for hardware resource allocation. |

> ⚠️ **Scientific Integrity Disclosure:** Continual learning under rare attack exposures faces catastrophic forgetting challenges. While Replay+EWC maintains overall stability (Accuracy = 0.8844), the Macro-F1 drops to 0.1762 during continual adaptation phases, which is documented as an open limitation of this research.

---

## 🛠️ Installation & Usage

### Prerequisites
```bash
pip install -r requirements.txt

```

### Temporal Windowing & Data Preprocessing

```bash
python preprocess.py --data_path ./data/UNSW-NB15/ --window_size 10

```

### Self-Supervised Pre-training (SSL)

```bash
python pretrain.py --epochs 50 --batch_size 256 --ssl_strategy masked_traffic

```

### Main Model Training & Open-Set Evaluation (LOAFO)

```bash
python train.py --protocol loafo --exclude_family Generic --seed 42

```

---

## 📝 Repository Structure

```text
├── data/               # Audited datasets directory
├── src/
│   ├── models/         # Network architectures (Transformer, BiLSTM, Adaptive Gate)
│   ├── ssl/            # Self-Supervised Learning mechanisms
│   ├── open_set/       # Class-Conditional Deep SVDD Gateway
│   ├── explainability/ # Explainable AI layers (Rollout & Integrated Gradients)
│   └── continual/      # Continual Learning strategies (EWC + Replay Buffer)
├── preprocess.py       # Robust preprocessing and temporal windowing pipeline
├── train.py            # Main script for multi-seed training and evaluation
├── requirements.txt    # Software dependency specifications
└── README.md           # Project documentation
