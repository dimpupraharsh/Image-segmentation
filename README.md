# Semantic Segmentation on COCO-2017 Subset using U-Net with ResNet50 Encoder

This project implements a semantic segmentation pipeline for identifying four object classes — **cake, car, dog, and person** — using a U-Net architecture with a **ResNet50 encoder** pretrained on ImageNet. The model is fine-tuned on a subset of the COCO-2017 dataset and evaluated using pixel-wise accuracy, Intersection over Union (IoU), and Dice coefficient.

---

## 📂 Dataset

- **Source**: [COCO-2017 Dataset](https://cocodataset.org)
- **Classes used**: `cake`, `car`, `dog`, `person`  
- **Split**:  
  - Training: 300 images  
  - Validation: 300 images  
  - Test: 30 images  
- **Annotations**: Provided in COCO JSON format (`labels.json` for train/val)

---

## 🧠 Model Architecture

- **Encoder**: ResNet50 (pretrained on ImageNet)
- **Decoder**: U-Net with skip connections and transposed convolutions
- **Custom Loss**: Weighted Sparse Categorical Crossentropy (to address class imbalance)
- **Mask Colors**:
  - Background: Black (0,0,0)
  - Cake: Red (255,0,0)
  - Car: Green (0,255,0)
  - Dog: Blue (0,0,255)
  - Person: Yellow (255,255,0)

---

## 🧪 Evaluation Metrics

| Metric             | Value     |
|--------------------|-----------|
| Pixel Accuracy     | 83.48%    |
| Mean IoU           | 0.5638    |
| Mean Dice          | 0.6020    |

### Per-Class IoU and Dice

| Class     | IoU    | Dice   |
|-----------|--------|--------|
| Background| 0.8247 | 0.8965 |
| Cake      | 0.7500 | 0.7500 |
| Car       | 0.1910 | 0.2402 |
| Dog       | 0.7188 | 0.7188 |
| Person    | 0.3343 | 0.4047 |

---

## 📊 Visual Results

Model predictions are visualized alongside ground truth masks for both validation and test sets. Each mask is color-coded according to the class legend.
<img width="988" alt="Screenshot 2025-06-18 at 5 27 00 PM" src="https://github.com/user-attachments/assets/44f7a640-138d-4a6d-8be7-575115472a0d" />


---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/semantic-segmentation-coco-subset.git
cd semantic-segmentation-coco-subset
