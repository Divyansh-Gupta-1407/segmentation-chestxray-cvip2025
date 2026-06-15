# segmentation-chestxray-cvip2025
A conference paper presented at CVIP 2025

# Benchmarking Deep Learning Architectures for Lung Segmentation in Chest X-Rays

A comparative study of advanced U-Net architectures for automated lung segmentation in chest X-ray images.

This work investigates the effectiveness of multiple deep learning segmentation models on a combined dataset of healthy and pathological chest X-rays, with the goal of improving Computer-Aided Diagnosis (CAD) workflows for pulmonary disease assessment.

---

## Overview

Accurate lung segmentation is a fundamental preprocessing step in many medical imaging applications, including:

* Tuberculosis screening
* Pneumonia assessment
* Pulmonary disease monitoring
* Computer-Aided Diagnosis (CAD) systems

This project benchmarks four widely used segmentation architectures and analyzes their performance using both overlap-based and boundary-based evaluation metrics.

---

## Research Objective

The primary objective of this study was to evaluate how modern U-Net variants perform when trained on a more diverse dataset created by combining multiple publicly available chest X-ray datasets.

The study focuses on:

* Segmentation accuracy
* Model generalization
* Boundary precision
* Clinical applicability

---

## Dataset

The training dataset was created by combining two government-approved public chest X-ray datasets:

### Montgomery County Dataset

* Healthy chest X-rays
* Tuberculosis-positive cases

### Shenzhen Dataset

* Healthy chest X-rays
* Tuberculosis-positive cases

### Dataset Statistics

* Total Images: 704
* Image Modality: Chest X-Ray
* Task: Lung Segmentation

---

## Data Preprocessing

The following preprocessing pipeline was applied:

* Image resizing to 256 × 256 pixels
* Bilinear interpolation
* Min-Max normalization
* Conversion to NumPy arrays for TensorFlow/Keras training

---

## Evaluated Architectures

### U-Net

The baseline encoder-decoder architecture commonly used in biomedical image segmentation.

### ResU-Net

Introduces residual blocks to improve gradient flow and enable deeper feature extraction.

### Attention U-Net

Utilizes attention gates to focus on relevant anatomical structures while suppressing irrelevant regions.

### U-Net++

Employs nested skip connections and dense feature aggregation to reduce the semantic gap between encoder and decoder features.

---

## Methodology

```text
Chest X-Ray Images
        │
        ▼
Data Preprocessing
        │
        ▼
Train / Validation Split
        │
        ▼
Model Training
        │
 ┌──────┼──────┬─────────┐
 ▼      ▼      ▼         ▼
U-Net ResU-Net Attention U-Net U-Net++
        │
        ▼
Performance Evaluation
        │
        ▼
Model Comparison
```

---

## Evaluation Metrics

The models were evaluated using both overlap-based and boundary-based metrics:

* Dice Coefficient
* Jaccard Index (IoU)
* F1 Score
* Hausdorff Distance (HD)
* Average Symmetric Surface Distance (ASSD)

---

## Results

| Model           | Dice Score | IoU        | F1 Score   |
| --------------- | ---------- | ---------- | ---------- |
| U-Net           | 0.9560     | 0.9151     | 0.9555     |
| ResU-Net        | 0.9627     | 0.9291     | 0.9631     |
| Attention U-Net | 0.9558     | 0.9149     | 0.9561     |
| U-Net++         | **0.9661** | **0.9343** | **0.9708** |

### Key Findings

* U-Net++ achieved the highest overall segmentation performance.
* Residual connections improved model stability and feature learning.
* Attention mechanisms provided selective feature enhancement but did not outperform U-Net++.
* Dense skip pathways in U-Net++ contributed to better boundary delineation and segmentation accuracy.

---

## Research Contributions

* Created a combined chest X-ray dataset for improved model generalization.
* Benchmarked four widely used segmentation architectures under identical experimental settings.
* Provided a comparative analysis using both overlap and boundary metrics.
* Demonstrated the effectiveness of U-Net++ for lung segmentation tasks.

---

## Publication

📄 Research Paper: *Benchmarking U-Net Variants for Lung Segmentation in Chest X-Rays*

(Add DOI, publication link, or PDF here)

---

## Tech Stack

* Python
* TensorFlow
* Keras
* NumPy
* OpenCV

---

## Future Work

* Evaluate transformer-based segmentation architectures
* Incorporate larger multi-institutional datasets
* Extend the study to multi-class lung abnormality segmentation
* Investigate real-time clinical deployment scenarios

---

## Authors

**Divyansh Gupta**

Co-authors and publication details can be added here.
