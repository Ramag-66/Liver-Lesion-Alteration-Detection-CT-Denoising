
# RiskMapUNet: Liver CT Denoising Error Localization 
CAN U ACHIEVE HIGHER? AND MORE ACCURATE? model

## Overview

RiskMapUNet is a deep learning model designed to identify liver regions where CT denoising increases reconstruction error. The project uses a pretrained RED-CNN model to denoise low-dose CT images and RiskMapUNet to predict regions of increased error.

The goal is to evaluate local changes introduced by denoising, rather than relying only on overall image-quality measurements.

## Methodology

The project follows four main steps:

1. **CT Denoising:** Apply pretrained RED-CNN to low-dose CT images.
2. **Pseudo-Label Generation:** Compare low-dose and denoised images against full-dose CT references to identify liver pixels where reconstruction error increases by more than 4 HU.
3. **Error Localization:** Train RiskMapUNet using low-dose CT, denoised CT, and their difference.
4. **Model Evaluation:** Compare RiskMapUNet with Attention U-Net and ResDUNet-inspired models using five-fold patient-level cross-validation.

## Results

| Model | Dice | IoU | AUC-PR |
|---|---:|---:|---:|
| Attention U-Net | 0.1823 | 0.1032 | 0.2014 |
| ResDUNet-inspired | 0.2565 | 0.1501 | 0.2140 |
| **RiskMapUNet** | **0.3109** | **0.1842** | **0.2175** |

RiskMapUNet achieved the highest scores among the compared models, although localization accuracy remains limited.

## Dataset

The project uses paired low-dose and full-dose CT images from the Mayo Clinic Low-Dose CT dataset, available through The Cancer Imaging Archive (TCIA).

## Technologies

- Python
- PyTorch
- RED-CNN
- U-Net architectures
- TotalSegmentator
- Medical CT image processing

## Limitations

The model identifies regions of increased reference error, not clinically confirmed lesions or tissue damage. Further evaluation and improvements are needed before clinical use.

## Purpose

This project was developed for academic research into the reliability of deep learning-based CT denoising.




CANN
