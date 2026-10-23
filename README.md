# TinyGPT — Build a Tiny Language Model from Scratch

> A beginner-friendly project to understand, train, and experiment with a **real language model** — without relying on ChatGPT, Gemini, Claude, or any pretrained AI model.

## Overview

TinyGPT is a learning-focused project where we'll build a **character-level language model** that learns patterns from text and predicts the next character. Once trained, it will generate text by repeatedly sampling its own predictions.

We'll start small and understandable, then improve the model step by step. The long-term goal is to explore how GPT-style models work, including **embeddings, backpropagation, context, and self-attention**.

**Current status:** Project planning / README only. The model, training scripts, and demo have **not been implemented yet**.

## Goals

- Learn how text is converted into tokens and token IDs.
- Prepare input/target sequences for next-character prediction.
- Build a small neural network ourselves with PyTorch.
- Understand forward passes, loss, gradients, and backpropagation.
- Train on a small text dataset using a CPU.
- Generate new text from a trained model.
- Evaluate results, then experiment with context length and self-attention.

## How TinyGPT will work

```text
Raw text
   |
   v
Character tokenizer --> Token IDs
   |
   v
Training sequences (input --> next character)
   |
   v
Small neural network
   |
   v
Predictions --> Loss --> Backpropagation --> Updated weights
   |
   v
Trained model --> New character predictions --> Generated text
```

For example, in the training text `catcat`, an input of `c` has `a` as its next-character target. A context-aware model can learn from longer inputs such as `ca` to predict `t`.

## Planned technology stack

| Tool | Why we'll use it |
| --- | --- |
| Python 3.11+ | Main programming language |
| PyTorch | Neural network training and automatic differentiation |
| NumPy | Small numerical experiments and learning exercises |
| Matplotlib *(optional)* | Visualizing training loss |
| VS Code or another editor | Writing and running code |

**Hardware:** We'll design the first model to train on a regular laptop CPU; a GPU is optional. Training speed will depend on dataset size and model configuration.

## Learning roadmap

- [ ] **Phase 1 — Tokenization:** Characters, vocabularies, token IDs, encoding, and decoding.
- [ ] **Phase 2 — Training data:** Context windows, inputs, and next-token targets.
- [ ] **Phase 3 — Baseline model:** Build a small next-character predictor.
- [ ] **Phase 4 — Neural network:** Embeddings, layers, predictions, and loss.
- [ ] **Phase 5 — Training loop:** Gradient descent, backpropagation, and checkpoints.
- [ ] **Phase 6 — Text generation:** Sampling, temperature, and prompts.
- [ ] **Phase 7 — Evaluation:** Compare generations and track training loss.
- [ ] **Phase 8 — Transformer concepts:** Introduce self-attention and experiment with a tiny GPT-style architecture.

## Planned repository structure

The structure below is a **plan**, not a list of files already created.

```text
TinyGPT/
├── README.md
├── data/                 # Small training text files
├── tinygpt/
│   ├── tokenizer.py      # Character-to-ID mapping
│   ├── model.py          # Language model
│   └── generate.py       # Text generation
├── train.py              # Training script
├── requirements.txt      # Python dependencies
└── examples/             # Exercises and outputs
```

## What makes this an actual AI project?

We won't just pass user text to an external AI API. We'll implement a model whose **parameters are updated by training on text data**. You will be able to inspect the token IDs, training loss, learned weights, and generated output.

The initial model will be educational and very small. It won't match the knowledge or capabilities of modern large language models, and generated text may be repetitive or imperfect.

## Getting started

For now, this repository only documents the plan. There are no installation commands or working training scripts yet.

Our **first implementation task** will be to build and test a character-level tokenizer in Python.

## Guiding principles

1. Understand each concept before adding complexity.
2. Write code ourselves; use libraries for math and training, not hosted AI inference.
3. Keep every stage small enough to run and debug on a laptop.
4. Measure learning with training loss and simple generation examples.
5. Prefer clear explanations and reproducible experiments over unnecessary features.

---

**TinyGPT is a learning project, not a production chatbot.**
