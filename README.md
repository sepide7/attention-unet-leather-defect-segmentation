# Attention U-Net for Automated Leather Defect Segmentation

This repository presents an attention-based U-Net architecture for pixel-level defect localization on leather surfaces. The project focuses on precise anomaly segmentation rather than defect classification and is designed for industrial surface inspection applications.

---

## 🔍 Problem Statement
Leather defect inspection is a challenging task due to complex textures, non-uniform illumination, and irregular defect patterns. Traditional rule-based methods often fail to generalize, while classification-based approaches lack spatial precision.

This work addresses the problem as a **semantic segmentation task**, enabling accurate localization of defective regions at the pixel level.

---

## 🧠 Methodology
The proposed model extends the classical U-Net architecture by integrating **attention gates** into skip connections. This allows the network to focus on defect-relevant spatial features while suppressing background noise.

Key components:
- Attention U-Net architecture
- Binary semantic segmentation
- Dice and IoU-based evaluation
- Lightweight design for industrial deployment

---

## 📊 Experimental Results
The attention-enhanced model demonstrates improved localization accuracy compared to the standard U-Net, particularly for small and low-contrast defects.

| Model | Dice | IoU |
|------|------|-----|
| U-Net | 0.41 | 0.28 |
| Attention U-Net | **0.53** | **0.43** |

Qualitative results show cleaner segmentation boundaries and reduced false positives in textured regions.

---

## 🏭 Industrial Relevance
The system is suitable for real-world leather inspection pipelines and can be adapted to other surface defect detection domains such as textiles, wood, and metal.

Potential applications include:
- Automated quality control
- Defect grading and rejection
- Process optimization in Industry 4.0 environments

---

## 📌 Limitations & Future Work
- Limited dataset size
- Sensitivity to lighting variations
- Manual annotation cost

Future directions include weakly supervised learning, multi-spectral imaging, and edge-device optimization.

---

## 📄 Related Publication
**Attention U-Net–Based Approach for Automated Leather Defect Detection**  
*Sepideh Khoshnood Afshari, Hakan Aktaş*  
(Under review / Published)

---

## 🛠️ Tech Stack
- Python
- TensorFlow / PyTorch
- OpenCV
- NumPy
- LabelMe

---
## 📬 Contact
**Sepideh Khoshnood Afshari**  
PhD Candidate – Electrical & Electronics Engineering  
📧 sepide.khoshnood@gmail.com
