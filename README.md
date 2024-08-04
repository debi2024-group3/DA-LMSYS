# Fine-Tuning LLMs for Human Preference Prediction

This project demonstrates how to fine-tune the DeBERTaV3 model ana LLama2 on the LMSYS dataset to predict human preferences in responses generated by large language models (LLMs).

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Setup](#setup)
- [Usage](#usage)
- [Fine-Tuning Process](#fine-tuning-process)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Introduction

DeBERTa (Decoding-enhanced BERT with Disentangled Attention) is a transformer model developed by Microsoft. This project focuses on fine-tuning DeBERTa to improve its performance on a specific task: predicting human preferences in LLM responses. The fine-tuning process leverages a portion of the LMSYS dataset.

## Features

- **Efficient Fine-Tuning**: Utilizes Low-Rank Adaptation (LoRA) to fine-tune the model efficiently.
- **Disentangled Attention Mechanism**: Enhances model performance by separating content and positional information.
- **Special Tokens Handling**: Incorporates special tokens for better task-specific adaptation.
- **Resource Optimization**: Freezes layers to reduce computational load and speed up training.

## Setup

### Prerequisites

- Python 3.7 or higher
- PyTorch
- Transformers
- Datasets
- Pandas

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/deberta-fine-tuning.git

2. Install the required packages:
pip install -r requirements.txt

### Usage
#### Dataset Preparation

   Ensure your LMSYS dataset is available in CSV format:
   
    data/lmsys_dataset.csv

#### Fine-Tuning

   Run the fine-tuning script:

    python fine_tune_deberta.py

### Inference

Use the fine-tuned model for inference on new data:

    python inference.py --input "path/to/your/input.csv" --output "path/to/your/output.csv"

### Fine-Tuning Process
Steps

- Load and Preprocess the Dataset: Convert the CSV data into a Hugging Face Dataset and select a portion for training.
- Load the Model and Tokenizer: Initialize the DeBERTa model and tokenizer, add special tokens.
-  Modify Output Layer: Adjust the classifier layer to match the number of labels.
- Freeze Layers: Freeze all layers except the classifier to reduce computational load.
- Tokenize Data: Tokenize the text columns using the tokenizer.
- Prepare Data for Training: Format the datasets for PyTorch.
- Define Training Arguments: Set up the training parameters.
- Train the Model: Use the Trainer API to fine-tune the model.
