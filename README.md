# Robotics-GPT 🤖

A lightweight, 13-million parameter GPT model trained entirely from scratch on ArXiv robotics and machine learning abstracts. 

**Note:** This project was built primarily as an educational exercise to implement and understand Attention mechanisms and Transformer architectures from the ground up using PyTorch.

[![Model Weights](https://img.shields.io/badge/Download-Model_Weights-blue?logo=googledrive)](https://drive.google.com/file/d/1MJMiDftRj9BYC1O1oLJeakEYN6TY04UC/view?usp=sharing)

##  Architecture

The model is a custom-built decoder-only Transformer (TinyTransformer) with the following specifications:
- **Layers:** 4
- **Attention Heads:** 4
- **Embedding Dimension (`d_model`):** 128
- **Context Size (`block_size`):** 128 tokens
- **Tokenizer:** BPE (OpenAI's `tiktoken` GPT-2 encoding, vocab size: 50,257)
- **Total Parameters:** ~13.7M

##  Dataset

The training corpus consists of **12,664 academic abstracts**. 
- Sourced from the `ccdv/arxiv-summarization` dataset.
- Filtered specifically for robotics and machine learning keywords (e.g., *robot, manipulation, reinforcement learning, policy, control, autonomous*).

## raining & Results

The model was trained to predict the next token using standard autoregressive language modeling.

- **Optimizer:** AdamW
- **Learning Rate:** Cosine decay schedule with warmup
- **Regularization:** Gradient clipping and Dropout (0.1)
- **Performance:** Cross-entropy loss decreased from **5.77 → 3.40** over 23,000 training steps.

Despite its small size, the model successfully learns the structure and vocabulary of academic papers and can generate plausible continuations for robotics research prompts.
