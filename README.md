# BridgeRL: Towards Optimal Pre-training Data Mixtures for Empowering Reinforcement Learning in LLMs

---

## 📖 Overview

This repository contains the proxy models and core fitting pipeline for **BridgeRL**, a framework designed to identify optimal pre-training data mixtures for empowering Large Language Model (LLM) reasoning through Reinforcement Learning (RL). 

While post-RL reasoning performance varies significantly across different base models, exhaustive full-scale training is computationally prohibitive. **BridgeRL** addresses this by:
1. Treating the search for optimal mixing ratios as a **regression task**.
2. Introducing **$avg(k-ppl)$** (the average perplexity of the base model over $k$ RL-generated responses) as a stable, algorithm-agnostic fitting objective.
3. Providing pre-trained lightweight **1M and 60M parameter proxy models** to enable efficient data-mixture fitting and performance prediction without training from scratch.

---

## 🗂️ Repository Structure

Since this repository focuses on providing proxy model checkpoints and the data-fitting pipeline, the directory is structured as follows:

```text
BridgeRL/
├── proxy_models/            # 1M and 60M proxy model checkpoints
├── requirements.txt         # Python dependencies
└── README.md
```

---

## 📦 Download Proxy Models

We provide pre-trained and RL-evaluated small-scale proxy models (1M and 60M parameters). Users can directly load these weights to extract proxy metrics ($avg(k-ppl)$) and run regression fitting for data mixture prediction.

| Model Size | Description |
| :--- | :--- |
| **1M Proxy** | 1M parameters, trained on diverse pre-training data mixtures |
| **60M Proxy** | 60M parameters, scaled across online/offline RL (GRPO/DPO) evaluations |

---

## 📊 Summary of Results

* **Predictor Stability:** $avg(k-ppl)$ significantly outperforms standard pre-training loss and pass@k metrics, yielding stronger Spearman correlation ($\rho$).
* **Downstream Gains:** Models trained on BridgeRL-predicted optimal data mixtures achieve consistent performance improvements on competitive reasoning benchmarks (e.g., HumanEval, MBPP, MATH) under both GRPO and DPO algorithms.

---

## 📝 Citation

If you find our work or proxy models helpful in your research, please consider citing our paper:

BibTeX will be released soon.