Protein–DNA/RNA Interaction Prediction:
This project implements a machine learning system that classifies protein sequences into four categories: DNA-binding, RNA-binding, dual DNA/RNA-binding (DRNA), or non-binding. The goal was to build an end-to-end prediction pipeline starting from raw amino-acid sequences and evaluate multiple model designs to improve classification performance.

The project was completed using RapidMiner and focuses on feature engineering, model comparison, and evaluation on class-imbalanced biological data.

Problem Overview:
Given a protein’s amino-acid sequence, the task is to predict whether the protein interacts with DNA, RNA, both, or neither. The dataset is highly imbalanced, with relatively few DRNA proteins, making evaluation and model selection especially important.

Data:
Training dataset: ~8,800 protein sequences with known interaction labels
Blind test dataset: ~8,800 unlabeled protein sequences
Input format: raw amino-acid sequences (variable length)
(Datasets were provided as part of a university course assignment.)

Feature Engineering:
Each protein sequence was converted into a fixed-length numeric feature vector, including:
Amino-acid counts and frequencies
Sequence length features
Biochemical group frequencies (hydrophobic, polar, acidic, basic, aromatic)
Motif-based indicators related to nucleic-acid binding
Ratio-based and derived features

Model Designs:
Three model designs were developed and evaluated using 5-fold cross-validation:
Design 1: Basic sequence composition features with a Decision Tree classifier
Design 2: Expanded biochemical features with a Decision Tree to measure feature impact
Design 3: Full feature set with Z-Normalization and a tuned Random Forest
Design 3 achieved the best overall performance and was selected for blind test prediction.

Evaluation based on:
Accuracy
Sensitivity and specificity (per class)
Matthews Correlation Coefficient (MCC)
Average MCC across all four classes
MCC was used as the primary metric due to class imbalance.

Blind Test Prediction:
The final Random Forest model was trained on the full training dataset and applied to the blind test dataset using a stored preprocessing and inference pipeline. Predictions were exported as a text file containing one predicted label per protein sequence.

Tools & Technologies:
RapidMiner
Decision Trees
Random Forest
Feature Engineering
Cross-Validation
Model Evaluation for Imbalanced Data



