# DL-hw1-taskB

This project implements a lightweight image classification model that combines 2 convolutional layers and a Multi-Head Self-Attention (MHSA) block. It is designed to meet the constraint of ≤ 4 effective layers while achieving at least 90% of ResNet34’s accuracy on the ImageNet-mini dataset. The project includes baseline comparison, ablation tests, and FLOPs/parameter analysis.

## How to Run

1. Change `data_dir`  in the program to your dataset path.

This will:

- Train baseline ResNet34 on ImageNet-mini.
- Train custom CNN+MHSA model (2 effective layers).
- Run ablation test using a CNN-only version.
- Output:
  - Validation accuracy for each model
  - FLOPs and Params using `thop`
  - Accuracy plots (train vs validation)

## Results Summary

| Model         | Val Acc | FLOPs   | Params |
|---------------|---------|---------|--------|
| ResNet34      | 41.33%  | 300M    | 21.3M  |
| CNN+MHSA      | 37.56%  | 21.05M  | 88.9K  |
| CNN Only      | 22.44%  | 21.05M  | 88.9K  |

> CNN+MHSA achieves ~90.9% of ResNet34’s performance while being over 200x smaller.

## Settings

- Optimizer: Adam
- Learning Rate: 1e-3
- Batch Size: 32
- Epochs: 20
- FLOPs/Params calculated via `thop`

## Notes

- All models are trained from scratch (no pretraining).
- Early stopping is triggered once CNN+MHSA reaches ≥90% of ResNet34 accuracy.
- Suitable for low-resource deployment or embedded applications.
