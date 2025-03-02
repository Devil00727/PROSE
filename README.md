# 3D CNN for Protein Structure-Based Masked Amino Acid Prediction

## Overview

Current state-of-the-art methods for encoding protein information rely on large language models (LLMs) that use amino acid sequences as input (e.g., ESM-1b1, ESM2, Prot-T5). While some approaches integrate 3D structural information, they do so only at the amino acid sequence level and do not truly capture the full 3D conformation of a protein's atoms.

This project aims to develop a 3D Convolutional Neural Network (3D CNN) that directly takes the 3D structure of proteins as input. Prior research (such as the work of the Wilke group: https://www.nature.com/articles/s41598-023-40247-w) suggests that information extracted in this manner can complement existing LLM-based embeddings.

The goal is to train a 3D CNN in a self-supervised manner on whole protein structures, generating meaningful numerical representations for downstream tasks such as masked amino acid prediction.

## Requirements

To run the project, install the necessary dependencies:

```
pip install numpy pandas torch torchvision biopython matplotlib
```

## Usage

1. **Prepare Input Data**: Use `Generate_input_matrix_local_subset.ipynb` to preprocess protein structures into the required input format (it takes input as PDB files)
2. **Train the Model**: Run `3DCNN_for_masked_AA_prediction.ipynb` to train the 3D CNN on the processed dataset.
3. **Evaluate & Use Representations**: Extract learned embeddings for protein analysis.
