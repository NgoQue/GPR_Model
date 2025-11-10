📄 README
🔍 Overview

This repository contains the dataset and code used to build a machine learning model for predicting the glass transition temperature (Tg) of polymers. The approach leverages Gaussian Process Regression (GPR) combined with a custom Tanimoto kernel, enabling high-accuracy prediction of Tg values based solely on polymer chemical structures.

🧪 Dataset

The source dataset contains 7174 polymers, covering experimental Tg values from 134 K to 768 K.

Dataset originates from:

M. J. Uddin and J. Fan, Polymers 16(8), 1049 (2024).
https://doi.org/10.3390/polym16081049

For this study, we selected a subset of 1586 polymers whose Tg values are below 320 K.
This range matches the Tg values of the target polymers: PPS, PI, PPG, and PB.

To verify that limiting Tg improves predictive performance, several training ranges (200–500 K, 200–600 K, full dataset) were evaluated. As shown in Table SIII of the Supplementary Materials, the 200–500 K training range yielded the highest prediction accuracy, while including high-Tg polymers caused systematic overestimation for low-Tg systems.

🧬 Molecular Representation

Polymers were represented using SMILES format (Simplified Molecular Input Line Entry System).

Molecular fingerprints (2048-bit binary vectors) were generated using RDKit.

Each bit in the fingerprint indicates the presence or absence of a specific structural motif.

🤖 Machine Learning Model

Gaussian Process Regression (GPR) with a custom Tanimoto kernel was used.

Dataset split: 80% training / 20% test (random shuffle).

Evaluation metrics:

R² (coefficient of determination) – measures how well the model captures variance.

RMSE (root mean square error) – measures average difference between predicted and experimental Tg.
