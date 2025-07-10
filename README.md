# Emotion Detection using Fine-Tuned BERT

**Author:** Diya Amith Kodappully  
**Student ID:** 22071849

---

## Project Overview

This project fine-tunes a pre-trained BERT model to classify emotions in text. The goal is to accurately identify one of six emotions — joy, sadness, anger, fear, love, and surprise — from English sentences. Emotion detection is useful for applications like mental health analysis, chatbots, and content moderation.

---

## Dataset

- **Source:** Hugging Face `emotion` dataset  
- **Description:** Contains ~20,000 English sentences labeled with six emotion classes.  
- **Splits:** 80% training, 10% validation, 10% testing.

---

## Features

- Fine-tunes `bert-base-uncased` model with a weighted loss function to handle class imbalance.
- Tokenizes text using BERT tokenizer with padding and truncation.
- Training monitored via validation accuracy and loss.
- Evaluation includes accuracy, precision, recall, and F1-score.
- Provides a simple pipeline for inference on custom text inputs.

---

## Installation

```bash
pip install transformers datasets evaluate scikit-learn seaborn matplotlib
