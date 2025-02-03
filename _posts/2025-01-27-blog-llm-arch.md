---
title: 'LLM Architecture Types'
date: 2025-01-27
permalink: /posts/2025/01/blog-llm-arch/
tags:
  - LLM
  - Transformer
  - NLP
---

LLM Types:
======
Based on different usage version of Transformer architecture, there are three type of LLM architectures:

1. Encoder Only Models
2. Encoder Decoder Models
3. Decoder Only Models

Encoder Only Models
------
- Also known as **Autoencoding Models**
- Trained using Masked Language Modeling (Denoising objective)
- Bidirectional context of input sequence
- Use Cases:
    - Sentiment analysis
    - Name entity recognition
    - Word classification 
- Examples:
    - BERT
    - ROBERTA

Encoder Decoder Models
------

Decoder Only Models
------

LLM Life Cycle:
======
1. Scope: Define the use case of a LLM model
2. Select: Choose an existing model or pretrain your own
3. Adapt/Align Model and Evaluation:
    1. Adapt and Align Model: 
        - Prompt Engineering / In-Context Learning
        - Fine Tuning / Instruct Fine-Tuning
        - Align with Human Feedback (RLHF)
    2. Evaluation
4. Application Intergration:
    1. Optimize and deploy model for inference
    2. Augment model and build LLM-powered applications