#  Oil Spill Semantic Segmentation Comparative Evaluation

### 🎯 Overview

This project conducts a rigorous comparative evaluation of two prominent semantic segmentation models for the task of **Marine Oil Spill Detection** using **Synthetic Aperture Radar (SAR)** imagery.

The goal is to find the optimal model architecture and backbone combination that effectively balances high detection **accuracy (mIoU)** with computational **efficiency (Inference Latency and Model Size)** for practical, potentially real-time, deployment.

---

### 💡 Task & Models

The comparison focuses on the trade-off between models optimized for detailed accuracy versus models optimized for resource efficiency.

| Model Architecture | Encoder Backbone | Primary Focus | Use Case Consideration |
| :--- | :--- | :--- | :--- |
| **UNet** | **ResNet-18** | High **Boundary Precision** and Accuracy | Deployment on server/cloud infrastructure where computational resources are plentiful. |
| **DeepLabV3+** | **MobileNetV3** | High **Computational Efficiency** and Multi-Scale Context | Real-time and edge-device deployment (e.g., drone or vessel computing). |

#### Architectural Key Differences:
* **UNet (U-Net):** Employs **skip connections** to directly fuse high-resolution, low-level features with upsampled, high-level features. This excels at precise boundary delineation.
* **DeepLabV3+:** Utilizes the **Atrous Spatial Pyramid Pooling (ASPP)** module to capture context at multiple scales, making it robust to variations in oil slick size and shape.

---

### 📂 Dataset and Classes

* **Target Dataset:** A public domain or custom **SAR Oil Spill Dataset** (e.g., MKLab SAR Oil Spill Dataset).
* **Segmentation Classes (Labels):** The models are trained to perform multi-class segmentation for a comprehensive scene understanding:
    1.  Sea Surface (Background)
    2.  **Oil Spill** (Primary Target Class)
    3.  Oil Look-alikes (e.g., wind shadows, biogenic slicks)
    4.  Ship
    5.  Land


