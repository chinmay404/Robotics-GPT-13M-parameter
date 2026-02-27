# Robotics-GPT

13M parameter GPT trained from scratch on 12,664 ArXiv robotics/ML abstracts.

## Architecture
- Transformer: 4 layers, 4 heads, d_model=128
- Tokenizer: BPE (tiktoken gpt2, vocab=50,257)
- Parameters: 13.7M
- Training: AdamW, cosine LR schedule, gradient clipping

## Dataset
12,664 ArXiv abstracts filtered for robotics and ML keywords
from the ccdv/arxiv-summarization dataset.

## Results
Loss: 5.77 → 3.40 over 23,000 steps
Generates academic paper continuations in robotics domain.
