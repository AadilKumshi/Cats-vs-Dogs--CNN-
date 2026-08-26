# Cats vs Dogs Classification using CNNs

A hands-on exploration of CNN architecture for binary image classification. Starting with the original basic architecture, the model was progressively modified to study the effects of depth, Batch Normalization, Global Average Pooling, dropout, and padding.

## Dataset

- ~20,000 training images
- Image size: 256 × 256 × 3
- Binary classification: Cat / Dog

## Results

| Model | Validation Accuracy |
|---|---:|
| Baseline Model | 79.58% |
| Custom CNN | 91.18% |
| CNN + GAP | 90.92% |
| Deeper CNN | 93.54% |
| Final CNN | **94.10%** |

## Final Architecture

```text
Input (256 × 256 × 3)
        ↓
Conv2D (32) → BatchNorm → MaxPool
        ↓
Conv2D (64) → BatchNorm → MaxPool
        ↓
Conv2D (128) → BatchNorm
Conv2D (128) → BatchNorm → MaxPool
        ↓
Conv2D (256) → BatchNorm
Conv2D (256) → BatchNorm → MaxPool
        ↓
Global Average Pooling
        ↓
Dense (128) → Dropout (0.5)
        ↓
Dense (64) → Dropout (0.3)
        ↓
Dense (1) → Sigmoid

```

The project focuses on understanding how architectural changes affect learning and generalization rather than simply maximizing accuracy.

**Tech:** Python, TensorFlow, Keras, NumPy, Matplotlib
