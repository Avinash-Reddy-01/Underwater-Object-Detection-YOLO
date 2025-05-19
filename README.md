# 🌊 Underwater Object Detection using Enhanced YOLO Models

This repository showcases enhanced object detection models based on the **YOLO architecture**, specifically tailored for detecting submerged objects in **Side Scan Sonar (SSS) imagery**.

The work is supported by the dataset and methodology published in:

📄 [Enhanced YOLO models for underwater object detection using side scan sonar imagery](https://www.sciencedirect.com/science/article/pii/S2352340924001045)

---

## 🚢 Overview

We implement and benchmark the following YOLO models:

- ✅ YOLOv8l
- ✅ YOLOv11-n (Nano) — **Best performing**
- ✅ YOLOv11-s (Small)
- ✅ YOLOv11-m (Medium)
- ✅ YOLOv11-l (Large)

The models were trained to detect objects like:
- **MILCO (Mine-Like Contact Objects)**
- **NOMBO (Non-Mine-Like Contact Objects)**

---

## 🔍 Dataset

- The core dataset was sourced from the **Data in Brief** article above.
- Additional object categories were incorporated from **open-source platforms**, including [Roboflow](https://universe.roboflow.com/) to improve generalization.
- The dataset is formatted for **YOLO-style detection** with labeled `.txt` annotation files for each image.

### `data.yaml` Overview:
```yaml
train: train/images
val: val/images
test: test/images

nc: 2
names: ['MILCO', 'NOMBO']
```

---

## 🧪 Best Performing Model

- 📈 **YOLOv11-n (Nano)** achieved the best trade-off between accuracy and speed.
- ✅ Lightweight, efficient for real-time underwater inference.
- 🧠 Trained weights: `yolo11n.pt`

---

## 🛠️ How to Use

1. **Clone the repository**
```bash
git clone https://github.com/Avinash-Reddy-01/Underwater-Object-Detection-YOLO.git
cd underwater-yolo
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Train a model**
```bash
yolo task=detect mode=train model=yolov11n.pt data=data.yaml epochs=100 imgsz=640
```

4. **Run inference**
```bash
yolo task=detect mode=predict model=yolov11n.pt source=images/
```

5. **Evaluate model**
```bash
yolo task=detect mode=val model=yolov11n.pt data=data.yaml
```

> 💡 Tip: You can also use `Object_Detection.ipynb` to run and visualize training/inference steps inside a Jupyter environment.

---

## ⚙️ Technologies Used

- Python
- YOLOv8 / YOLOv11 (Ultralytics)
- PyTorch
- Roboflow (for additional datasets)
- OpenCV
- Jupyter Notebooks

---

## 📧 Contact

**Avinash Reddy**  
📨 avinashreddykasireddy954@gmail.com

---

## 📝 License

This project is licensed under the **MIT License**.

---
