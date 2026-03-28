# Deep Learning Model Comparison: CNN vs. Transformer Architectures

## Project Overview
[cite_start]This repository contains the implementation and rigorous evaluation of state-of-the-art deep learning architectures for image classification[cite: 13]. The project systematically compares convolutional neural networks (CNNs) against vision transformers (ViTs) to analyze performance, computational efficiency, and robustness under distribution shifts.

[cite_start]This project was developed as part of the CSE 475 Machine Learning course at East West University[cite: 1, 2].

## Dataset
* **Name:** Tropical Flower Dataset
* **Size:** ~4,319 images
* **Classes:** 7 (Bougainvillea, Crown of thorns, Hibiscus, Jungle geranium, Madagascar periwinkle, Marigold, Rose)
* [cite_start]**Integration:** Integrated directly via Kaggle `input` directories to ensure strict execution reproducibility[cite: 56].

## Architectures Evaluated
The evaluation is split into two distinct experimental pipelines:

### 1. Convolutional Neural Networks (CNNs)
* [cite_start]**MobileNetV3:** Optimized for mobile and edge deployment[cite: 15, 108].
* [cite_start]**ResNeXt-50:** Evaluated for grouped convolutions and cardinality[cite: 15, 108].
* [cite_start]**EfficientNet-B3:** Evaluated for compound scaling of depth, width, and resolution[cite: 15, 108].

### 2. Vision Transformers
* [cite_start]**Vision Transformer (ViT):** Baseline patch-based self-attention[cite: 17, 143].
* [cite_start]**Swin Transformer:** Evaluated for shifted-window hierarchical feature extraction[cite: 17, 143].
* [cite_start]**DeiT (Data-efficient Image Transformers):** Evaluated for knowledge distillation token efficiency[cite: 17, 143].

## Engineering Pipeline & Methodology
To ensure industry-standard reproducibility and performance, the training infrastructure implements:
* [cite_start]**Deterministic Execution:** Strict global seeding across Python, NumPy, PyTorch, and cuDNN to guarantee reproducible results upon `Run All` execution[cite: 23, 24].
* [cite_start]**Advanced Augmentation:** Implementation of `RandAugment` alongside standard affine transformations to prevent background-feature overfitting[cite: 119, 153].
* [cite_start]**Optimization Scheduling:** Optimizer-specific tuning (SGD/Adam for CNNs; AdamW with Warmup and Cosine Annealing for Transformers)[cite: 121, 155].
* [cite_start]**Compute Efficiency:** Mixed-precision training (`torch.cuda.amp`) utilized to optimize GPU VRAM consumption[cite: 29, 155].

## Results & Comparative Analysis (WIP)

### Performance Metrics
*Note: This table will be updated upon completion of the 30-epoch training cycles.*

| Architecture | Parameters | Top-1 Accuracy | Macro F1-Score | Inference Time (ms/batch) |
| :--- | :--- | :--- | :--- | :--- |
| MobileNetV3 | [TBD] | [TBD] | [TBD] | [TBD] |
| ResNeXt-50 | [TBD] | [TBD] | [TBD] | [TBD] |
| EfficientNet-B3 | [TBD] | [TBD] | [TBD] | [TBD] |
| ViT | [TBD] | [TBD] | [TBD] | [TBD] |
| Swin | [TBD] | [TBD] | [TBD] | [TBD] |
| DeiT | [TBD] | [TBD] | [TBD] | [TBD] |

### Robustness & Distribution Shifts
[cite_start]Models are subjected to synthetic distribution shifts (Gaussian Noise, Brightness/Contrast variations) to evaluate feature degradation[cite: 132]. 
* *Detailed robustness curves and degradation analysis will be published in the final notebooks.*

### Error Analysis
[cite_start]We utilize Attention Map visualization (for Transformers) and Softmax confidence mapping to systematically diagnose misclassifications and expose architectural blind spots[cite: 165, 169].

## Links to Reproducible Code
Both notebooks are hosted and executable on Kaggle (P100/T4x2 GPU environments):
* **Notebook 1 (CNNs):** [INSERT KAGGLE PUBLIC URL HERE]
* **Notebook 2 (Transformers):** [INSERT KAGGLE PUBLIC URL HERE]

---
**Authors:**
* Nabil (Group [XX]) - [Insert ID]
* [Partner Name] - [Insert ID]