Here's the corrected structure of your project, with improvements in the index and overall format for clarity and consistency:

---

# Project: Text Summarization and Text Classification

## Index:
1. [Overview](#overview)
2. [Main File: Text Summarization (Finetune Google T5 on Billsum dataset.ipynb)](#main-file-text-summarization)
   - [Steps](#steps)
   - [Challenges](#challenges)
   - [Usage](#usage)
   - [Results](#results)
   - [Open the File Directly](#open-text-summarization-file)
3. [Secondary File: Text Classification (Fine tuning  distilbert-base-uncased with Imdb.ipynb)](#secondary-file-text-classification)
   - [Features](#features)
   - [Instructions](#instructions)
   - [Output](#output)
   - [Open the File Directly](#open-text-classification-file)

---

## Overview

This project demonstrates the use of two NLP techniques: **Text Summarization** and **Text Classification**. The **Text Summarization** file is the primary focus, showcasing how the **T5 model** is used to summarize California state bills from the BillSum dataset. The **Text Classification** file demonstrates how **DistilBERT** can be fine-tuned for sentiment analysis as an additional example.

---

## Main File: Text Summarization

![Screenshot 2024-10-12 001113](https://github.com/user-attachments/assets/05541343-8c4f-4281-ba37-ef8e58fedd47)

This file covers the core task of the project: summarizing text using the **T5 model**. Below are the main aspects of the file:

### Steps

1. **Dataset**: We use the **BillSum** dataset (`ca_test` split) for summarization.
2. **Model**: We employ the **T5-small** model, fine-tuning it with the **Seq2SeqTrainer**.
3. **Evaluation**: The model's performance is measured using **ROUGE** scores.
4. **Inference**: Summaries are generated using both non-finetuned and finetuned versions of the model for comparison.

### Challenges

- **Training Time**: The training process was lengthy and required a high-performing GPU.
- **Memory Issues**: Encountered frequent OOM (Out of Memory) errors during training.

### Usage

To run the summarization task, follow these steps:

1. Install the required dependencies:
   ```bash
   pip install transformers datasets evaluate
   ```
2. Fine-tune the model using the provided script and run inference.

### Results

![Screenshot 2024-10-12 025153](https://github.com/user-attachments/assets/932df9b6-f8c2-45aa-b3b3-7b9179b459d1)

The **finetuned model** delivers better-quality summaries than the non-finetuned model, as observed through the results.

### Open Text Summarization File
[Link to the file](#) <!-- Add the actual link to your GitHub file here -->

---

## Secondary File: Text Classification

This file provides an additional demonstration of **Text Classification** using **DistilBERT**, primarily for sentiment analysis on the IMDb dataset. While it adds value to the project, it remains secondary to the summarization task.

### Features

- **Model**: Fine-tuning **DistilBERT** for sequence classification.
- **Dataset**: IMDb dataset for binary sentiment classification (positive/negative).
- **Fine-tuning**: Uses **LoRA (Low-Rank Adaptation)** for parameter-efficient fine-tuning with PEFT.

### Instructions

1. Install the necessary dependencies:
   ```bash
   !pip install peft evaluate datasets transformers torch
   ```
2. Load and prepare the **IMDb dataset**:
   ```python
   from datasets import load_dataset
   imdb_dataset = load_dataset("imdb")
   ```
3. Fine-tune **DistilBERT**:
   ```python
   model_checkpoint = 'distilbert-base-uncased'
   ```

### Output

The model provides accuracy metrics on the test dataset, evaluating its performance in classifying text as either positive or negative sentiment.

![Screenshot 2024-10-12 024648](https://github.com/user-attachments/assets/7a4ae42c-d7ef-4a79-b1b4-bd9284806854)

### Open Text Classification File
[Link to the file](#) <!-- Add the actual link to your GitHub file here -->

---

### Additional Notes

The **Text Summarization** task is the main focus of this project, while the **Text Classification** file is included as a secondary demonstration. The text classification task serves as an additional reference for users interested in understanding how LLMs can be applied to sentiment analysis tasks.

---
