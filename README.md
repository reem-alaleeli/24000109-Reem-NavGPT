# Reproducibility and Extension of NavGPT: Explicit Reasoning in Vision-and-Language Navigation  

**Original Paper:**  
NavGPT: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models  
Gengze Zhou, Yicong Hong, Qi Wu (AAAI 2024)

**Links:**  
- Paper: https://arxiv.org/pdf/2305.16986  
- AAAI Proceedings: https://ojs.aaai.org/index.php/AAAI/article/view/28597  
- Original Repository: https://github.com/GengzeZhou/NavGPT

## Overview

This repository contains the **reproducibility study, experiments and extension** for **AI501 Assignment 2**.

NavGPT is a zero-shot Large Language Model (LLM) agent for **Vision-and-Language Navigation (VLN)** on the Room-to-Room (R2R) benchmark. It uses:

- Textual observations of environments  
- Explicit reasoning (`Thought → Action`)  
- Step-by-step navigation decisions  

## Central Claim Reproduced

Large Language Models can perform **explicit reasoning for navigation**, including:

- Instruction understanding  
- Landmark recognition  
- Progress tracking  
- Sequential decision-making  

## Our Implementation

Instead of relying on closed models like GPT-4, this work uses:

- **Groq API**
- **LLaMA 3.1 (8B Instant)**  
- Custom **NavGPT-style reasoning agent (EnhancedNavGPT)**  
- Optimized pipeline for reproducibility and efficiency

## 🔬 Our Contributions

### Part A — Reproducibility
- Implemented a **NavGPT-style reasoning pipeline**
- Conducted **multi-seed experiments**
- Simulated VLN trajectories using R2R instructions
- Evaluated performance using **Success Rate (SR)**

### Part B — Critical Evaluation
- Identified key limitations:
  - LLM nondeterminism
  - Lack of real visual grounding (text-only observations)
  - Performance sensitivity to prompt/history size
- Observed **latency vs reasoning trade-off**

### Part C — Extension (Major Contribution)

- Replaced GPT-based models with:
  - **LLaMA 3.1 via Groq**
- Developed:
  - **Fast NavGPT pipeline (5–10× faster)**
  - **Bounded reasoning memory (efficient prompts)**
  - **Reproducible evaluation setup**

## Key Improvements Over Original Setup

| Feature         | Original NavGPT       | This Work                 |
|-----------------|-----------------------|---------------------------|
| Model           | GPT-4 / GPT-3.5       | LLaMA 3.1 (Groq)          |
| Cost            | High                  | Low / Free-tier           |
| Speed           | Slow                  | Fast (optimized)          |
| Reproducibility | Limited               | Strong                    |
| Pipeline        | Simulator-dependent   | Lightweight LLM-only      |

## Experimental Setup

- Dataset: R2R (Room-to-Room)
- Evaluation: Simplified navigation simulation
- Metrics:
  - Success Rate (SR)
  - Reasoning Length (proxy for reasoning quality)

### Experiments:
- Multi-seed reproducibility
- Temperature sensitivity analysis

---

## 🔬 Key Findings

### 1. Reasoning Emerges Clearly

Thought: The instruction asks me to move forward towards a sofa...
Action: move forward


### 2. Trade-off: Reasoning vs Efficiency
- Longer reasoning → better decisions  
- But → slower inference  

### 3. Temperature Sensitivity
- Low temperature → deterministic reasoning  
- Higher temperature → more exploratory reasoning  
- Moderate values perform best  

### 4. Limitations
- No real visual grounding (text-only observations)
- Simplified success metric (not full SPL)
- No full simulator integration

## Repository Structure

NavGPT-Reproducibility/
├── NavGPT.ipynb
├── "Key cited papers"/
├── datasets/
│   └── R2R/
├── NavGPT/
│   └── nav_src/
├── results/
├── figures/
├── logs/
└── README.md

## ▶️ How to Run

### 1. Setup
- Open Google Colab
- Run all notebook blocks sequentially

### 2. Dataset
- Automatically downloaded via Dropbox script

### 3. API Setup
- Enter your Groq API key when prompted

### 4. Run Experiments
- Reproducibility experiment
- Enhanced NavGPT experiment
- Temperature sensitivity analysis

### 5. Outputs
- Results → `/results`
- Logs → `/logs`
- Figures → `/figures`

## 📊 Visualizations

Generated automatically:

- Temperature vs Success Rate  
- Reasoning Length vs Temperature  

## Citation

```bibtex
@inproceedings{zhou2024navgpt,
  title={NavGPT: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models},
  author={Zhou, Gengze and Hong, Yicong and Wu, Qi},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  volume={38},
  number={7},
  pages={7641--7649},
  year={2024}
}
