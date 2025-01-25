![image](https://github.com/user-attachments/assets/753a6db4-f217-411f-aef3-43eaa78ff8d5)

# Parameter-Efficient Fine-Tuning (PEFT)

This repository provides a comprehensive guide to Parameter-Efficient Fine-Tuning (PEFT) methods, enabling efficient adaptation of large language models (LLMs) to specific tasks while minimizing memory and compute requirements. Traditional fine-tuning can be impractical for large models due to the need for substantial GPU memory and the overhead of storing separate model copies. PEFT addresses these challenges by modifying only a small fraction of model parameters, often less than 1% of the total model size.

---

## Overview of PEFT Methods

### LoRA (Low-Rank Adaptation)
LoRA is one of the most widely adopted PEFT techniques. It works by freezing the base model weights and introducing small, trainable matrices to the attention layers. This approach:
- Reduces trainable parameters by up to 90%.
- Maintains comparable performance to full fine-tuning.
- Allows efficient fine-tuning even on consumer hardware.

We demonstrate how to fine-tune LLMs using LoRA, load pre-trained LoRA adapters, and merge adapters into base models for deployment.

---

### Prompt Tuning
Prompt tuning is a lightweight PEFT method that optimizes trainable prompt tokens prepended to the input text while keeping the base model frozen. This technique:
- Is highly efficient for low-resource and multi-task scenarios.
- Achieves strong performance on larger models (e.g., >10B parameters).
- Allows rapid task switching by swapping prompt vectors.

---

## Notebooks in This Repository

The repository includes notebook explore and implement PEFT methods:

### LoRA Fine-Tuning
- **Description**: Fine-tune large language models using LoRA adapters.
- **Highlights**:
  - Train a model with LoRA for memory-efficient fine-tuning.
  - Experiment with rank values and configurations.
- **Notebook**: [LoRA Fine-Tuning](./notebooks/finetune_sft_peft.ipynb)

---

### Loading and Merging LoRA Adapters
- **Description**: Explore how to load pre-trained LoRA adapters and merge them into base models for deployment.
- **Notebook**: [Loading LoRA Adapters](./notebooks/load_lora_adapter.ipynb)

---

## Why Use PEFT?

PEFT methods are ideal for scenarios requiring resource efficiency, such as:
- Fine-tuning LLMs on consumer-grade GPUs.
- Multi-task learning with minimal memory overhead.
- Rapid prototyping and adaptation to new domains.
- Privacy-sensitive applications where full model fine-tuning is infeasible.

---

## Key Features of This Repository

1. **Memory Efficiency**: Demonstrates techniques like LoRA and QLoRA to reduce memory requirements for fine-tuning.
2. **Flexibility**: Offers tools to adapt models to diverse tasks with minimal overhead.
3. **Deployment Readiness**: Guides on merging adapters into base models for seamless deployment.
