# 🚀 YOLOv8 Object Detection for Industrial Safety Environments

> **YOLOv8 Object Detection for Industrial Safety. A shared-task machine learning project using YOLOv8l to detect Fire Extinguishers, Toolboxes, and Oxygen Tanks with 85.1% mAP@0.5. Includes training notebook, evaluation visuals, and full technical paper.**  
> Developed as part of a university-level ML competition  
> 📍 FAST NUCES Karachi · 🧑‍💻 Hani Siraj

---

## 📌 Project Summary

This project applies the **YOLOv8l** object detection model to identify three critical object types frequently found in industrial and safety-critical environments:

- 🔥 Fire Extinguisher  
- 🧰 Toolbox  
- 🧪 Oxygen Tank

The pipeline covers end-to-end stages: **data preparation**, **augmentation**, **training**, **fine-tuning**, and **evaluation** — with a strong focus on real-world robustness including occlusion handling and lighting challenges.

---

## 🧠 Objective

Build an accurate and efficient object detection model using **YOLOv8**, and optimize it to achieve the highest possible **mAP@0.5** score under practical constraints.

---

## 📁 Dataset

- **Total Images**: 1,139
- **Classes**: 3 (Balanced)
- **Format**: YOLO-annotated bounding boxes
- **Split**: 80% Training / 20% Validation
- **Preprocessing**:
  - Resizing to 640x640
  - Class balancing
  - Label smoothing
  - Occlusion-aware augmentation

---

## ⚙️ Model Configuration

| Setting         | Value              |
|----------------|--------------------|
| Model           | YOLOv8l            |
| Image Size      | 640x640            |
| Epochs          | 50                 |
| Batch Size      | 16                 |
| Optimizer       | SGD                |
| Learning Rate   | 0.005              |
| Augmentation    | Mosaic, HSV, Flip  |
| Label Smoothing | 0.1                |
| Early Stopping  | Enabled (patience 5)|

---

## 📈 Performance

- **Final mAP@0.5**: **85.1%**

| Problem                     | Fix Applied                          | Result         |
|----------------------------|--------------------------------------|----------------|
| Occlusion hurting recall   | Occlusion-aware augmentation         | +7% Recall     |
| Early overfitting          | Early stopping & tuned epochs        | +3% Precision  |
| Minor class imbalance      | Weighted sampling                    | +1% mAP        |
| Lighting variation         | HSV brightness + label smoothing     | Better robustness |

---

## 🔍 Results & Visuals

### 📊 Training Metrics

*Include your loss curves, mAP plots here*

![Training Curve Placeholder](./assets/training_curve.png)

---

### 🔎 Sample Detections

*Predictions on validation images*

![Detections Placeholder](./assets/sample_detections.png)

---

### 🔀 Confusion Matrix

*Highlight class-wise confusion*

![Confusion Matrix Placeholder](./assets/confusion_matrix.png)

---

### ❌ Failure Cases

Despite strong performance, the model struggled in the following scenarios:

- **Low Lighting**: Toolbox detection was often missed in dark conditions.
- **Partial Occlusion**: OxygenTanks frequently went undetected when partially hidden.

These failure modes informed targeted augmentations such as HSV tuning and occlusion-aware transforms.

Our output
![Failure Cases](./assets/failure_cases.png)
Given Labels
![Failure Cases](./assets/failure_cases.png)

Here the model is unable to predict the toolbox in low lighting (first image) which is clearly shown in the labels(second image)
Adjusted parameters for better detection in low light
hsv_h=0.015,
hsv_s=0.7,
hsv_v=0.7,  # Increased value (brightness)
Mosaic = 0.8

---

## 📄 Full Technical Paper

Read the full shared task-style research paper with methodology, results, and improvements:

📄 [View the Paper on Overleaf (LaTeX)](https://www.overleaf.com/read/your-share-link)  
📥 [Download as PDF](https://your-pdf-download-link)

---

## 👨‍💻 Author

**Hani Siraj**  
AI Undergraduate — FAST NUCES Karachi  
📧 hanisiraj@email.com  
🌐 [LinkedIn](https://www.linkedin.com/in/your-profile) · [Portfolio](https://your-site.com)

---

## 📌 Future Work

- Try YOLOv9 (anchor-free) for benchmark comparison
- Use SAM (Segment Anything Model) for better ROI selection
- Apply `evolve` for hyperparameter tuning
- Convert model to TorchScript or ONNX for deployment

---

## 🤝 Acknowledgment

Project developed with support from fellow students at FAST NUCES Karachi.  
[Teammates: Hasan Abdul - k228727@nu.edu.pk
Sajad ali - k228729@nu.edu.pk]

---

