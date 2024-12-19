# CheckMate 

## What is CheckMate?

CheckMate is the Jupyter Notebook code clone detection application for professors and teachers.

![Siamese Network](https://github.com/user-attachments/assets/ee83093d-e45c-4f46-bf57-42762526cd73)


## Datasets

Python code clone detection
https://researchdata.ntu.edu.sg/dataset.xhtml?persistentId=doi:10.21979/N9/VPCR7H#

## Why we used CodeBERT?
- State-of-the-art embeddings for code representation.
- Pre-trained on massive datasets of code (Python, Java, etc.).
- Supports extracting embeddings for code snippets to compute cosine similarity directly.
- Available with HuggingFace's Transformers library, which makes it easy to use.

## Why we used Siamese Network?

- contrastive learning and synthetic code

Recommendation
For Synthetic Data: If you're primarily working with synthetic pairs of code, and if the clones have similar structural patterns (e.g., only minor syntactic differences such as variable renaming or refactoring), then AST-based models might be better. They will help the model focus on structural similarity and ignore superficial differences in the code, such as variable names or formatting changes.

For More Nuanced Clones: If you are dealing with semantic clones that involve different code patterns or more significant transformations (e.g., different algorithms solving the same problem), a Siamese network might be more effective, especially if you use pretrained embeddings (e.g., CodeBERT, CodeT5, or Sentence-BERT).

You can also combine both approaches:

Use AST-based models to generate structural embeddings and then pass them through a Siamese network to perform pairwise similarity learning. This would allow you to capture both structural and semantic similarities.

Summary:
AST-based models are better for detecting structural clones with synthetic data where the focus is on identifying subtle differences in code logic (e.g., variable renaming, refactoring).
Siamese networks are better for detecting semantic clones, especially if the code snippets are not just syntactically different but also semantically different, even when the underlying task is the same.
