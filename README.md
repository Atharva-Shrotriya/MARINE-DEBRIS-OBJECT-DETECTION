# MARINE-DEBRIS-OBJECT-DETECTION
Absolutely! Based on the research paper titled **"Marine Debris Object Detection using YOLOv12"**, here's a professional and informative README content you can use for your GitHub repository:

---

# 🌊 Marine Debris Detection Using YOLOv12

### 🧠 Overview
This project leverages **YOLOv12**, the latest evolution in real-time object detection, to identify and classify marine debris from satellite and underwater imagery. It addresses the growing environmental challenge of ocean pollution by providing a scalable, automated solution for detecting items like plastic bags, gloves, nets, and more.

---

## 🎯 Objectives
- Detect and classify marine debris using deep learning  
- Evaluate YOLOv12 variants for accuracy vs. computational cost  
- Enable real-time monitoring for environmental surveillance  

---

## 🛠️ Technologies Used
- Python 3.8+  
- PyTorch 1.12.0  
- CUDA 11.6 (Tesla T4 GPU)  
- YOLOv12 architecture  
- OpenCV for image processing  

---

## 📁 Dataset
The model is trained on the **UW Garbage Debris Dataset**, which includes:
- 5,130 annotated underwater images  
- 15 debris categories (e.g., plastic bags, gloves, metal, nets)  
- Bounding boxes and centroid annotations for robust learning  

---

## 🧪 Model Architecture
YOLOv12 introduces several innovations:
- **Backbone**: 7×7 depthwise separable convolutions with C3k2 modules  
- **Neck**: A2C2f module with Area Attention and residual connections  
- **Head**: Position-aware convolutions and dynamic MLP ratio adjustment  
- **Detection**: Anchor-free, multi-scale prediction optimized for small objects  

---

## ⚙️ Training Configuration

| Hyperparameter | Value         |
|----------------|---------------|
| Epochs         | 50            |
| Batch Size     | 8, 16         |
| Optimizer      | AdamW         |
| Learning Rate  | 0.000526      |

Training was conducted on Google Colab using a Tesla T4 GPU.

---

## 📊 Performance Comparison

| Model      | Params | GFLOPS | mAP@0.5 | mAP@0.5:0.95 |
|------------|--------|--------|---------|--------------|
| YOLOv12n   | 2.7M   | 11.7   | 0.263   | 0.136        |
| YOLOv12m   | 19.6M  | 59.5   | 0.825   | 0.527        |
| YOLOv12l   | 43.6M  | 164.9  | 0.817   | **0.530**    |

YOLOv12l achieved the highest accuracy, while YOLOv12m offered the best balance between performance and efficiency.


---

## 🚀 Usage

### Run Detection
```bash
python detect.py --source data/test.jpg --weights yolov12l.pt --conf 0.5
```

### Train Model
```bash
python train.py --data data.yaml --epochs 50 --batch-size 16
```

---

## 🌐 Applications
- Autonomous underwater vehicles (AUVs)  
- Satellite-based ocean monitoring  
- Environmental research and policy-making  
- Real-time surveillance for coastal cleanup operations  

---


---

Would you like help adding visualizations, demo videos, or deployment instructions next? That could really elevate the presentation.
