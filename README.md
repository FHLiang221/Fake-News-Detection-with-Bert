# CAIS++ Mini Project Writeup

**Name:** Freddie Liang
**Email:** fhliang@usc.edu

## Project Overview
This project implements a BERT-based fake news detection system capable of classifying news articles as real or fake by analyzing combined title and text content, achieving over 99% accuracy.

## Dataset
- Source: "Fake News Detection Datasets" from Kaggle
- Preprocessing:
  - Combined title and text fields into a single field
  - Applied 80/20 train/test split (35,918 training, 8,980 test samples)
  - Tokenization using BERT tokenizer with max length 256
- Reasoning: Dataset provides balanced, labeled examples with sufficient context for robust classification

## Model Development and Training
- Architecture: BERT-base-uncased with linear classifier layer
- Implementation Details:
  - Dropout rate: 0.1 for regularization
  - AdamW optimizer
  - CrossEntropyLoss function
- Hyperparameters:
  - Learning rate: 2e-5
  - Batch size: 8
  - Epochs: 4
  - Max sequence length: 256 tokens
- Reasoning: Choices justified by BERT fine-tuning best practices and GPU memory constraints

## Model Evaluation
Metrics and Results:
- Final validation accuracy: 99.98%
- Final validation loss: 0.0007
- Training loss: 0.0026
- Consistent improvement across epochs indicates stable training but also the possibility of overfitting to the dataset.

## Discussion

### Fitness for Task
The approach demonstrates strong task alignment:
- BERT effectively captures linguistic nuances and contextual relationships
- Dataset size sufficient for fine-tuning
- High accuracy and low loss indicate strong model confidence

### Wider Implications and Limitations
Potential Impact:
- Could help combat online misinformation
- Assist fact-checkers and news organizations

Limitations:
- Dataset may not represent evolving fake news patterns
- Potential bias from training data
- Need for continuous updating as misinformation tactics change

### Future Steps
1. Enhance robustness:
   - Test on diverse news sources
   - Implement cross-validation
2. Improve interpretability:
   - Add attention visualization
