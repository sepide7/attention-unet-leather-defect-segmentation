# Technical Overview

## 1. Problem Definition

Leather surface inspection is a critical quality control step in the leather manufacturing industry. Defects such as scratches, holes, wrinkles, and texture inconsistencies are often subtle, irregular, and visually similar to normal leather patterns.

Traditional rule-based computer vision methods fail to generalize due to high texture variability, while manual inspection is time-consuming, subjective, and prone to inconsistency. Therefore, an automated, pixel-level defect localization approach is required to enable reliable and scalable industrial inspection.


## 2. Dataset Description

The dataset consists of high-resolution leather surface images collected under controlled industrial lighting conditions. Each image is paired with a pixel-level ground truth mask indicating defective regions.

Key characteristics of the dataset include:
- Complex and repetitive background textures
- Significant variation in defect size, shape, and appearance
- Class imbalance between defect and non-defect pixels

All images are preprocessed to ensure consistent input resolution and normalized intensity distributions prior to training.

## 3. Model Architecture

The proposed model is based on the U-Net encoder–decoder architecture, designed for pixel-level semantic segmentation tasks. To improve defect localization in complex leather textures, an attention mechanism is integrated into the skip connections.

### 3.1 Baseline U-Net

The baseline architecture follows a symmetric encoder–decoder structure with skip connections that preserve spatial information lost during downsampling.

### 3.2 Attention Mechanism

Attention gates are applied to the skip connections to selectively emphasize relevant feature regions while suppressing background noise. This mechanism enables the network to focus on defect-prone areas and reduces false positives caused by repetitive leather textures.

### 3.3 Final Architecture

The final model combines multi-scale feature extraction with attention-guided feature fusion, resulting in improved localization accuracy without significantly increasing computational complexity.


## 4. Training Strategy

The model is trained using supervised learning with pixel-level annotations. Data augmentation techniques such as random flipping, rotation, and intensity variation are applied to improve generalization across different leather textures.

Training is performed using mini-batch gradient descent with early stopping based on validation performance to prevent overfitting. The learning rate is adjusted dynamically to stabilize convergence.


## 5. Loss Functions

Due to the strong class imbalance between defect and non-defect pixels, a combination of region-based and pixel-wise loss functions is employed. This strategy encourages accurate boundary localization while maintaining robustness against sparse defect regions.


## 6. Evaluation Metrics

Model performance is evaluated using segmentation-specific metrics, including Intersection over Union (IoU) and Dice coefficient. These metrics provide a balanced assessment of both region overlap and boundary accuracy, which are critical for industrial inspection tasks.


## 7. Experimental Results

## 8. Industrial Applicability

## 9. Limitations and Future Work
