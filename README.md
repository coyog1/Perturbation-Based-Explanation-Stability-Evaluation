# Perturbation-Based-Explanation-Stability-Evaluation
This repository contains the code and experiments for the thesis project titled **"Perturbation-Based Analysis of Explanation Stability in Time Series Models"**. The goal of this project is to evaluate how various perturbation strategies and similarity metrics affect the stability of explanations produced by XAI methods for time series classification models.

---

## 🧠 Overview

Post hoc, model-agnostic XAI methods like LIMESegment provide local explanations for complex machine learning models. This project introduces a detection score framework that assesses how reliably different similarity metrics can detect attribution shifts under a variety of input perturbations.

We evaluate:
- **5 perturbation methods**
- **5 similarity metrics**
- Across **2 model architectures** (CNN and LSTM)
- On **2 time series datasets** (FordA and FordB)

---

## 📁 Repository Structure
data/                          # Raw and preprocessed data
results/                       # Result files (e.g., plots, output data)

MODEL_FordA.ipynb              # CNN model on FordA
MODEL_FordB.ipynb              # CNN model on FordB
MODEL_LSTM_FordA.ipynb         # LSTM model on FordA
MODEL_LSTM_FordB-NEW.ipynb     # LSTM model on FordB

Untitled-*.ipynb               # Intermediate experiments / metric calculations
Results.ipynb                  # Aggregated result visualizations and analysis
README.md                      # This file
venv/                          # Virtual environment and requirements

---

## 📊 Datasets

We use the **FordA** and **FordB** datasets from the UCR Time Series Classification Archive:

- [FordA Dataset](https://www.timeseriesclassification.com/description.php?Dataset=FordA)
- [FordB Dataset](https://www.timeseriesclassification.com/description.php?Dataset=FordB)

---

## 📦 Setup

To set up the environment, run:

```bash
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r venv/requirements.txt

---

## 🚀 Running the Code

You can run the experiments by opening and executing the notebooks in the root directory. Suggested order:

- `MODEL_FordA.ipynb` / `MODEL_FordB.ipynb`: Train CNNs on Ford datasets.
- `MODEL_LSTM_FordA.ipynb` / `MODEL_LSTM_FordB-NEW.ipynb`: Train LSTMs.
- `Untitled-*.ipynb`: Run perturbations and compute similarity metrics.
- `Results.ipynb`: Aggregate scores and plot detection heatmaps.

## 📘 Methodology Summary

- Explanations are generated using **LIMESegment**.
- **Input perturbations**: value masking, contiguous masking, amplitude scaling, phase shifting, frequency masking.
- **Similarity metrics**: cosine similarity, circular cross-correlation (CCC), spectral correlation, Fourier distance, and Earth Mover’s Distance (EMD).
- A **detection score** is calculated to assess how reliably each metric responds to explanation changes.

## 📄 License

This project is for academic purposes and provided under the **MIT License**.

## 👤 Author

**[Your Name]**  
Master’s Thesis – *[Your University / Department]*  
Supervised by: *[Supervisor Name]*

## ✨ Acknowledgments

- UCR Time Series Classification Archive  
- LIMESegment paper by Sivill & Flach (2022)

