# NIDS Deep Learning Engine

**1D Convolutional Neural Network for Network Intrusion Detection**

[![Accuracy](https://img.shields.io/badge/Accuracy-99.91%25-4a9e5e?style=for-the-badge&labelColor=0a0809)]()
[![Dataset](https://img.shields.io/badge/Dataset-KDD_Cup_1999-c0273f?style=for-the-badge&labelColor=0a0809)]()
[![Framework](https://img.shields.io/badge/Framework-TensorFlow-c0273f?style=for-the-badge&labelColor=0a0809)]()

---

## Overview

Real-world network traffic classification engine built to catch zero-day and dynamic attacks. Built as the CT Lab final project for B.Tech CSE (Data Science) at MITAOE.

**Role:** Lead Architect — designed, built, and evaluated the full pipeline.

---

## Results

| Metric | Value |
|--------|-------|
| Accuracy | 99.91% |
| Total Parameters | 156,805 |
| Training Samples | 395,216 |
| Testing Samples | 98,805 |
| Output Classes | 5 (Normal, DoS, Probe, R2L, U2R) |

---

## Model Architecture

    Input (41x1)
        |
    Conv1D (64 filters, kernel=3, ReLU)
        |
    MaxPooling (pool=2)
        |
    Conv1D (128 filters, kernel=3, ReLU)
        |
    MaxPooling (pool=2)
        |
    Flatten --> 1024 values
        |
    Dense (128 neurons, ReLU)
        |
    Dropout (0.3)
        |
    Dense Output (Softmax, 5 classes)

**Optimizer:** Adam
**Loss:** Sparse Categorical Crossentropy
**Epochs:** 10

---

## Dataset

KDD Cup 1999 — 10% sample slice

- 41 features (numerical + categorical)
- Features include: duration, protocol_type, src_bytes, flag, and 37 others
- 5 traffic classes: Normal, DoS, Probe, R2L, U2R

---

## Key Insight

U2R class showed 82% precision — identified as a **dataset statistical artifact** (only 12 test samples in that class) rather than a model failure. Perfect precision and recall achieved for DoS and Normal traffic.

---

## Run It

Open in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](YOUR_COLAB_LINK_HERE)

Or locally:

    git clone https://github.com/ruushhdaa/NIDS-Deep-Learning-Engine.git
    cd NIDS-Deep-Learning-Engine
    pip install -r requirements.txt
    jupyter notebook nids_model.ipynb

---

## Part Of

This project is featured in my portfolio:
**[ruushhdaa.github.io/digital-portfolio](https://ruushhdaa.github.io/digital-portfolio)**

---

**Rushda Jagtap · MITAOE · B.Tech CSE Data Science · 2025**
