# Technical Overview

## Attention U-Net–Based Approach for Automated Leather Defect Segmentation

### Authors

**Assist. Prof. Dr. Hakan AKTAŞ**
Niğde Ömer Halisdemir University, Computer Engineering, Türkiye
ORCID: 0000-0002-0188-7075

**Sepideh Khoshnood Afshari (MSc Candidate)**
Niğde Ömer Halisdemir University, Electrical & Electronics Engineering, Türkiye
ORCID: 0009-0001-4898-5684

---

## 1. Problem Definition

Leather surface inspection is a critical quality control stage in leather manufacturing. Defects such as scratches, holes, wrinkles, color variations, and texture inconsistencies are often subtle, irregular, and visually similar to normal leather patterns. These characteristics make reliable inspection challenging.

Traditional rule-based computer vision approaches struggle to generalize due to high texture variability, while manual inspection is labor-intensive, subjective, and prone to inconsistency. Therefore, a robust **automated pixel-level defect localization** method is required to enable scalable and reliable industrial inspection.

This study formulates leather defect detection as a **semantic segmentation problem**, focusing on precise spatial localization of defects rather than defect type classification.

---

## 2. Dataset Description

A real-world dataset of **140 high-resolution leather surface images** was collected from industrial production facilities under controlled lighting conditions. Each image is paired with a pixel-level ground truth mask indicating defective regions.

**Dataset characteristics:**

* Complex and repetitive background textures
* Significant variation in defect size, shape, and appearance
* Strong class imbalance between defect and non-defect pixels

All images were preprocessed through normalization and resizing to **512×512** resolution to ensure consistent input dimensions and stable training behavior. The dataset was split into **70% training** and **30% testing** sets.

---

## 3. Model Architecture

The proposed method is based on the **U-Net encoder–decoder architecture**, which is widely used for semantic segmentation tasks due to its ability to preserve spatial information while capturing multi-scale features.

### 3.1 Baseline U-Net

The baseline U-Net consists of a symmetric encoder–decoder structure with skip connections that transfer spatial features from the encoder to the decoder. Initial experiments with this baseline model demonstrated **limited segmentation accuracy**, particularly for small and low-contrast leather defects.

### 3.2 Attention Mechanism

To address this limitation, **attention gates** were integrated into the skip connections. These attention units selectively emphasize defect-relevant features while suppressing irrelevant background information caused by repetitive leather textures.

This mechanism enables the network to dynamically focus on defect-prone regions, significantly reducing false positives and improving boundary localization.

### 3.3 Final Architecture

The final Attention U-Net architecture combines multi-scale feature extraction with attention-guided feature fusion. This design improves defect localization accuracy without introducing significant computational overhead, making it suitable for industrial deployment.

---

## 4. Training Strategy

The model was trained using supervised learning with pixel-level annotations. To enhance generalization across varying leather textures, **data augmentation** techniques such as random flipping, rotation, and intensity variation were applied.

Training was conducted using mini-batch gradient descent with:

* Dynamic learning rate scheduling
* Early stopping based on validation performance

Due to hardware constraints and the 512×512 input resolution, a small batch size was used. All experiments were conducted using **GPU acceleration**, and the model was iteratively tested, debugged, and refined.

---

## 5. Loss Functions

Given the severe class imbalance between defect and non-defect pixels, region-sensitive loss formulations were employed. The training process emphasized accurate boundary localization while maintaining robustness against sparse defect regions.

---

## 6. Evaluation Metrics

Model performance was evaluated using standard semantic segmentation metrics:

* **Intersection over Union (IoU)**
* **Dice Similarity Coefficient (DSC)**

These metrics provide a balanced assessment of both region overlap and boundary accuracy, which are essential for industrial inspection tasks.

---

## 7. Experimental Results

Experimental results demonstrate that incorporating attention mechanisms significantly improves segmentation performance compared to the baseline U-Net.

| Model           | Dice       | IoU        |
| --------------- | ---------- | ---------- |
| U-Net           | 0.4124     | 0.2803     |
| Attention U-Net | **0.5270** | **0.4261** |

Qualitative evaluations show cleaner segmentation boundaries and reduced false detections in highly textured regions. While some training instability was observed due to computational limitations, the attention-based model consistently outperformed the baseline.

---

## 8. Industrial Applicability

The proposed system is suitable for integration into **automated leather inspection pipelines**. Its pixel-level output enables downstream industrial decision-making such as defect grading, rejection, and process optimization.

The architecture is lightweight enough for near real-time inference and is **material-agnostic**, allowing adaptation to other surface inspection domains including textiles, wood, and metal.

---

## 9. Limitations and Future Work

Despite improved localization performance, the model may experience degradation under extreme lighting variations or when encountering unseen defect types.

Future research directions include:

* Multi-spectral and NIR data integration
* Model compression for edge and embedded deployment
* Weakly supervised learning to reduce annotation costs

---

## 10. Conclusion

This study demonstrates that integrating attention mechanisms into the U-Net architecture substantially enhances leather defect localization performance. While the baseline U-Net produced limited accuracy on complex textures, the Attention U-Net effectively focuses on defect-relevant regions, resulting in significant improvements in IoU and Dice metrics.

The proposed approach offers a practical and scalable solution for high-precision industrial surface inspection and provides a strong foundation for future research and cross-domain applications.
