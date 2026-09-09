# 🛡️ VisionGuard

### AI-Powered Content Moderation for Smart Glasses

VisionGuard is an **AI-powered real-time content moderation system designed for smart glasses and wearable cameras**. It analyzes images captured through wearable devices, detects people and potentially sensitive content, and makes an automated **ALLOW, UNCERTAIN, or BLOCK** decision before the content is permanently stored.

The system combines computer vision and multiple content-safety models to provide an additional privacy and safety layer for wearable-camera applications.

---

## 🔗 Project Repositories

### Frontend

[VisionGuard Frontend](https://github.com/Kishorem6002/Vision_Gaurd_Frontend)

### Backend

[VisionGuard Backend](https://github.com/Kishorem6002/VisionGaurd_backend)

---

## 🎯 Problem Statement

Smart glasses and wearable cameras can continuously capture images from the user's surroundings. Permanently storing every captured frame can create privacy and safety risks, especially when sensitive or explicit content is unintentionally recorded.

VisionGuard addresses this problem by introducing an **AI moderation layer between image capture and permanent storage**.

```text
Smart Glasses / Wearable Camera
            ↓
       Image Capture
            ↓
      VisionGuard AI
            ↓
   Person Detection
            ↓
 Content Risk Assessment
            ↓
    Decision Fusion
            ↓
 ┌──────────┼──────────┐
 ↓          ↓          ↓
ALLOW    UNCERTAIN    BLOCK
 ↓          ↓          ↓
Store     Review     Reject
```

---

## ✨ Key Features

* 🕶️ **Smart Glasses / Wearable Camera Support**
* 👤 **Person Detection**
* 🔍 **Sensitive Content Detection**
* 🤖 **Multi-model AI Analysis**
* ⚡ **Real-time Content Moderation**
* 🛡️ **Privacy-focused Storage Control**
* 🚦 **ALLOW / UNCERTAIN / BLOCK Classification**
* 📊 **Analysis Results and Moderation Status**
* 🔌 **REST API-based Backend**
* 🌐 **Web-based Monitoring Interface**

---

## 🧠 AI Pipeline

VisionGuard follows a multi-stage moderation pipeline:

### 1. Image Preprocessing

Captured images are prepared for AI analysis.

### 2. Human Detection

The system identifies people present in the captured image.

### 3. Adaptive Region Processing

Relevant regions containing people can be isolated for more focused analysis.

### 4. Content Risk Assessment

Multiple AI models analyze the image for potentially sensitive content.

### 5. Decision Fusion

The outputs from the detection models are combined to determine the final moderation decision.

### 6. Final Classification

| Decision         | Meaning                                    |
| ---------------- | ------------------------------------------ |
| 🟢 **ALLOW**     | Content is considered safe                 |
| 🟡 **UNCERTAIN** | Further review or analysis may be required |
| 🔴 **BLOCK**     | Sensitive content detected                 |

---

## 🤖 AI Models & Computer Vision

VisionGuard integrates multiple computer-vision and content-moderation components, including:

* **YOLOv8**
* **FalconsAI NSFW Detector**
* **Freepik NSFW Detector**
* **NudeNet**
* **NSFW Image Detection**
* **OpenCV**
* **PyTorch**
* **Ultralytics**

The backend repository also includes a `yolov8m.pt` model and dependencies for Ultralytics, NudeNet, NSFW image detection, OpenCV, PyTorch, NumPy, and related processing libraries.

---

## 🏗️ System Architecture

```text
                ┌─────────────────────┐
                │   Smart Glasses     │
                │  / Wearable Camera  │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   VisionGuard       │
                │     Frontend        │
                │ React + Vite        │
                └──────────┬──────────┘
                           │
                           │ REST API
                           ▼
                ┌─────────────────────┐
                │   FastAPI Backend   │
                └──────────┬──────────┘
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
        YOLOv8        NSFW Models     NudeNet
             │             │             │
             └─────────────┼─────────────┘
                           ▼
                ┌─────────────────────┐
                │  Decision Fusion    │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │ ALLOW / UNCERTAIN / │
                │       BLOCK         │
                └─────────────────────┘
```

---

## 💻 Technology Stack

### Frontend

* React.js
* Vite
* Axios
* React Router

The frontend repository uses React, React DOM, React Router DOM, Axios, Vite and the React Vite plugin.

### Backend

* Python
* FastAPI
* Uvicorn
* SQLAlchemy
* PostgreSQL
* PyTorch
* Ultralytics YOLO
* NudeNet
* NSFW Image Detector
* OpenCV
* Pillow
* Transformers
* NumPy
* Pandas

These dependencies are listed in the backend repository's `requirements.txt`.

---

## 📁 Repository Structure

### Frontend

```text
Vision_Gaurd_Frontend/
│
├── public/
├── src/
├── .env.example
├── index.html
├── package.json
├── package-lock.json
└── vite.config.js
```

### Backend

```text
VisionGaurd_backend/
│
├── Ultralytics/
├── api/
├── database/
├── migrations/
├── moderator/
├── schemas/
├── services/
├── main.py
├── requirements.txt
├── yolov8m.pt
└── test_storage.py
```

The current repositories contain these frontend and backend structures respectively.

---

## 🚀 Getting Started

### 1. Clone the repositories

```bash
git clone https://github.com/Kishorem6002/Vision_Gaurd_Frontend.git
git clone https://github.com/Kishorem6002/VisionGaurd_backend.git
```

### 2. Backend Setup

```bash
cd VisionGaurd_backend

python -m venv venv
```

Activate the environment on Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the backend:

```bash
uvicorn main:app --reload
```

### 3. Frontend Setup

```bash
cd Vision_Gaurd_Frontend

npm install
npm run dev
```

The frontend is configured as a Vite React application.

---

## 🔐 Environment Variables

Create the required `.env` files based on the provided `.env.example` files in the respective repositories.

Do not commit sensitive credentials, database passwords, API keys, or other secrets to GitHub.

---

## 🔄 Moderation Workflow

```text
Capture Image
      ↓
Preprocess Image
      ↓
Detect Person
      ↓
Extract Relevant Regions
      ↓
Run Content Moderation Models
      ↓
Combine Model Results
      ↓
Calculate Risk
      ↓
┌────────┬───────────┬────────┐
│ ALLOW  │ UNCERTAIN │ BLOCK  │
└────────┴───────────┴────────┘
      ↓
Storage Decision
```

---

## 🎯 Applications

VisionGuard can be applied to:

* Smart glasses
* Wearable cameras
* Personal safety devices
* Privacy-aware camera systems
* Real-time content moderation
* Edge/wearable computer-vision applications
* Automated media-storage filtering

---

## 🔮 Future Enhancements

* Edge deployment directly on smart-glass hardware
* Real-time video-stream moderation
* Hardware-level camera integration
* Model optimization for low-latency inference
* ONNX/TensorRT optimization
* Improved multi-person analysis
* Audio and multimodal moderation
* Advanced privacy-preserving storage
* Offline moderation capabilities

---

## 👨‍💻 Project

**VisionGuard**
AI-powered content moderation for smart glasses and wearable cameras.

### Repositories

* **Frontend:** https://github.com/Kishorem6002/Vision_Gaurd_Frontend
* **Backend:** https://github.com/Kishorem6002/VisionGaurd_backend
