
# Robotics-GPT — 13M Parameter Language Model
[![Model Weights](https://img.shields.io/badge/Download-Model_Weights-blue?logo=googledrive)](https://drive.google.com/file/d/1MJMiDftRj9BYC1O1oLJeakEYN6TY04UC/view?usp=sharing)
A GPT-style language model trained from scratch on ArXiv robotics 
and ML research abstracts.

## What This Is
Base language model that learns to generate academic paper continuations 
in the robotics/ML domain. Built to understand transformer architecture 
deeply before working with VLA models in robot learning.

## Architecture
- 4 Transformer layers, 4 attention heads
- d_model = 128, FFN hidden = 512
- BPE tokenization (tiktoken gpt2, vocab = 50,257)
- Causal masking, dropout = 0.1
- Total parameters: 13.7M

## Training
- Dataset: 12,664 ArXiv abstracts (robotics + ML filtered)
- Tokens: 16.2M
- Optimizer: AdamW (lr=3e-4, weight_decay=0.1)
- LR Schedule: Cosine decay with linear warmup (100 steps)
- Gradient clipping: 1.0
- Steps: 23,000
- Final loss: ~3.40

## Sample Output
Prompt: "We propose a novel approach to robot manipulation using"
Output: "...a coupled sensing function whose orientation of the 
network...we consider the average time of a narrow bonds..."

## Built From Scratch
No HuggingFace models used. Architecture implemented in pure PyTorch:
- Multi-head attention with causal masking
- Residual connections + LayerNorm
- Positional embeddings
- Full training infrastructure
