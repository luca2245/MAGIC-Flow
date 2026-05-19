# MAGIC-Flow

**MAGIC-Flow** is a conditional multiscale normalizing flow model that performs **both image generation and classification** within a single modular framework. It is specifically designed to handle challenging domains like medical imaging, where robust generative and discriminative capabilities are crucial.  

---

## Features

- **Generative modeling**: Generate high-quality, diverse samples conditioned on class labels.  
- **Synthetic dataset generation**: Create and save new datasets using the generation module.
- **Classification**: Predict class probabilities using the same flow-based framework.    
- **Likelihood attribution maps**: Visualize which regions of an image contribute most to classification predictions.  

---

## Folder Structure

The repository contains **two main folders**:

1. **`generation/`**:  
   - Train generative models.  
   - Generate new samples conditioned on class labels.  
   - Generate and save synthetic datasets.  
   - Use the **training script** for training and the **testing script** for inference and generation.

2. **`classification/`**:  
   - Train classification models.  
   - Assess prediction accuracy on validation/test sets.  
   - Visualize likelihood attribution maps for interpretability.  
   - Use the **training script** for model training and the **testing script** for evaluation.

---

## Dataset Structure

MAGIC-Flow expects the dataset to be organized as follows:

```text
dataset/
├── train/
│   ├── class_1/
│   │   ├── image1.png
│   │   ├── image2.png
│   │   └── ...
│   ├── class_2/
│   │   └── ...
│   └── ...
├── val/
│   ├── class_1/
│   │   └── ...
│   ├── class_2/
│   │   └── ...
│   └── ...
└── test/
    ├── class_1/
    │   └── ...
    ├── class_2/
    │   └── ...
    └── ...
```