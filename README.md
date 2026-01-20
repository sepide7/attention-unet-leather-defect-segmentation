# Attention U-Net for Automated Leather Defect Segmentation

This repository presents an attention-based U-Net architecture for pixel-level defect localization on leather surfaces.  
The project focuses on **precise anomaly segmentation** rather than defect classification and is designed for real-world industrial surface inspection applications.

---

## 🔍 Problem Statement

Leather defect inspection is a challenging task due to:
- Complex natural textures
- Non-uniform illumination
- Small, irregular, and low-contrast defects

Traditional rule-based inspection methods often fail to generalize across different leather types, while classification-based deep learning approaches lack spatial precision.

This work formulates leather defect inspection as a **semantic segmentation problem**, enabling accurate pixel-level localization of defective regions.

---

## 🧠 Methodology

### Baseline Experiment: U-Net

The study initially employed a **standard U-Net architecture** as a baseline segmentation model.

**Observation:**

> Baseline U-Net produced limited segmentation accuracy on small and low-contrast leather defects.

Although the baseline model captured global structural information, it struggled to consistently highlight subtle defect regions, particularly in visually complex or textured areas.

---

### Attention-Enhanced Model

To address these limitations, **attention gates** were integrated into the skip connections of the U-Net architecture.

> To address this limitation, attention gates were integrated into the skip connections, enabling the model to focus on defect-relevant regions.

The attention mechanism suppresses irrelevant background activations while amplifying spatial features that are more likely to correspond to defect regions.  
This architectural enhancement significantly improves defect localization and boundary precision.

---

### Training and Implementation Details

- Architecture: Attention U-Net
- Task: Binary semantic segmentation
- Loss Functions:
  - Binary Cross-Entropy
  - Dice Loss
- Evaluation Metrics:
  - Dice Score
  - Intersection over Union (IoU)
- Framework: TensorFlow / Keras
- Input: RGB leather surface images
- Output: Pixel-wise defect masks

> All experiments were conducted using GPU acceleration and the model was iteratively debugged and refined.

The entire pipeline was implemented, tested, and optimized on a local GPU-enabled system.  
Multiple training strategies and architectural adjustments were evaluated through systematic experimentation.

---

## 📊 Experimental Results

Quantitative evaluation demonstrates a clear performance improvement after incorporating attention mechanisms.

| Model | Dice | IoU |
|------|------|-----|
| U-Net | 0.41 | 0.28 |
| Attention U-Net | **0.53** | **0.43** |

Qualitative results show:
- Improved detection of small defects
- Cleaner segmentation boundaries
- Reduced false positives in textured background regions

---

## 🏭 Industrial Relevance

The proposed system is suitable for deployment in real-world leather inspection pipelines and can be adapted to other surface defect detection domains such as:
- Textile inspection
- Wood surface analysis
- Metal defect detection

Potential industrial applications include:
- Automated quality control
- Defect grading and rejection
- Smart manufacturing systems (Industry 4.0)

---

## 📌 Limitations & Future Work

**Current limitations:**
- Limited dataset size
- Sensitivity to lighting variations
- High cost of pixel-level annotations

**Future directions:**
- Weakly supervised or semi-supervised segmentation
- Multi-spectral (RGB + NIR) imaging
- Lightweight optimization for edge devices
- Cross-material generalization studies

---

## 📄 Related Publication

**Attention U-Net–Based Approach for Automated Leather Defect Detection**  
*Sepideh Khoshnood Afshari, Hakan Aktaş*  
(Published / Under Review)

---

## 🛠️ Tech Stack

- Python
- TensorFlow / Keras
- OpenCV
- NumPy
- LabelMe

---
## 📜 License
This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---
## 📬 Contact

**Sepideh Khoshnood Afshari**  
PhD Candidate – Electrical & Electronics Engineering  
📧 sepide.khoshnood@gmail.com
