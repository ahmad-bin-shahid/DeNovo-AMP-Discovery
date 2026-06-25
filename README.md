# DeNovo-AMP-Discovery

A deep learning framework for de novo antimicrobial peptide (AMP) discovery using Variational Autoencoders (VAEs), physicochemical feature engineering, and machine learning-based screening.

## Overview

The rapid emergence of antimicrobial resistance (AMR) has created an urgent need for novel antimicrobial compounds. Antimicrobial peptides (AMPs) represent promising therapeutic candidates due to their broad-spectrum activity and reduced susceptibility to resistance mechanisms.

This project explores the use of generative AI for AMP design by learning latent representations of known AMP sequences and generating novel peptide candidates for downstream screening.

---

## Objectives

- Learn latent representations of AMP sequences using a Variational Autoencoder (VAE)
- Generate novel peptide candidates through latent-space sampling
- Extract biologically relevant physicochemical properties
- Build predictive AMP classification models
- Prioritize high-confidence candidates for further investigation

---

## Methodology

### 1. Data Collection

AMP sequences were collected from publicly available peptide databases and subjected to preprocessing and quality control.

### 2. Sequence Encoding

Peptide sequences were converted into fixed-length one-hot encoded representations suitable for neural network training.

### 3. Variational Autoencoder (VAE)

A VAE was trained to:

- Compress peptide sequences into a latent space
- Learn underlying AMP sequence patterns
- Generate novel peptide candidates by sampling latent vectors

### 4. Physicochemical Feature Engineering

For each peptide, key AMP-associated properties were calculated:

- Net Charge
- Hydrophobicity
- Hydrophobic Moment
- Aromaticity
- Molecular Weight
- Isoelectric Point (pI)
- Boman Index
- Aliphatic Index
- GRAVY Score

### 5. AMP Classification

Multiple machine learning models were evaluated for AMP prediction:

| Model | Accuracy |
|---------|---------|
| SVM | 94.94% |
| Random Forest | 94.03% |
| Dual-Branch MLP | 93.50% |
| XGBoost | 93.50% |
| Dual-Branch LSTM | 92.30% |

Support Vector Machine achieved the highest validation accuracy.

### 6. Candidate Screening

Generated peptides were screened using:

- AMP probability scores
- Physicochemical feature profiles
- Similarity filtering
- Diversity analysis

Top candidates were prioritized for downstream validation.

---

## Results

### VAE Training

- Stable convergence observed
- Reconstruction loss consistently decreased
- No evidence of mode collapse
- Well-structured latent space learned

### Latent Space Analysis

UMAP projection demonstrated meaningful organization of peptide representations and successful learning of sequence relationships.

### Candidate Generation

The trained VAE generated hundreds of unique peptide candidates with diverse sequence compositions and AMP-like physicochemical properties.

### AMP Prediction

Best-performing classifier:

**Support Vector Machine (SVM)**
- Validation Accuracy: **94.94%**

---

## Technologies Used

### Deep Learning

- PyTorch
- Variational Autoencoders (VAE)

### Machine Learning

- Scikit-Learn
- XGBoost

### Bioinformatics

- Biopython
- Pandas
- NumPy

### Visualization

- Matplotlib
- Seaborn
- UMAP

---

## Project Workflow

```text
AMP Dataset
      │
      ▼
Sequence Preprocessing
      │
      ▼
One-Hot Encoding
      │
      ▼
VAE Training
      │
      ▼
Latent Space Learning
      │
      ▼
Novel Peptide Generation
      │
      ▼
Feature Extraction
      │
      ▼
AMP Classification
      │
      ▼
Candidate Ranking
      │
      ▼
Top AMP Candidates
