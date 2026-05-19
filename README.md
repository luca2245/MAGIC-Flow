# MAGIC-Flow

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-orange)
![Medical%20Imaging](https://img.shields.io/badge/Domain-Medical%20Imaging-lightgrey)

**MAGIC-Flow** is a conditional multiscale normalizing flow model that performs **both image generation and classification** within a single modular framework.

It is designed for challenging domains such as **medical imaging**, where robust generative and discriminative capabilities are crucial.

---

## Features

- **Conditional image generation**: Generate high-quality and diverse samples conditioned on class labels.
- **Synthetic dataset generation**: Create and save new datasets using the generation module.
- **Likelihood-based classification**: Classify images by evaluating class-conditional likelihoods.
- **Modular pipeline**: Separate generation and classification notebooks while preserving the same flow-based framework.
- **Application-specific masking**: Use custom masks designed for the tasks described in the paper.

---

## Repository Structure

```text
MAGIC-Flow/
├── README.md
│
├── classification/
│   ├── coupling_layer_cls.ipynb
│   ├── data_loader.ipynb
│   ├── magic_flow_model.ipynb
│   ├── testing.ipynb
│   └── training.ipynb
│
├── generation/
│   ├── coupling_layer_gen.ipynb
│   ├── data_loader.ipynb
│   ├── magic_flow_model.ipynb
│   ├── testing.ipynb
│   └── training.ipynb
│
└── custom_png/
    ├── coronal_slice_110_rotated.png
    └── seg_coronal_mask_padded.png
```

---

## Folder Structure

The repository contains three main folders:

1. **`generation/`**  
   - Train generative models.
   - Generate new samples conditioned on class labels.
   - Generate and save synthetic datasets.
   - Use `training.ipynb` for training and `testing.ipynb` for inference and generation.

2. **`classification/`**  
   - Train classification models.
   - Evaluate prediction performance on validation/test sets.
   - Use `training.ipynb` for model training and `testing.ipynb` for evaluation.

3. **`custom_png/`**  
   - Contains application-specific masks used for the tasks described in the paper.

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

Each split — `train`, `val`, and `test` — must contain one subfolder per class.  
The class folder names are used as labels.