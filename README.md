# 👗 AI-Powered Clothing Try-On System

This project implements a deep learning-based **virtual try-on system** that takes in a person image and a clothing item, and generates a realistic try-on output — without requiring the original garment worn.

![Try-On Preview](preview.gif)

---

## 🧠 Key Features

- Generates try-on images using a combination of:
  - Human Parsing
  - Pose Estimation (MMPose)
  - Agnostic Image Generation
  - U-Net-based Generator
- Based on the **VITON dataset** (front-facing, single-person setup)
- Modular pipeline built using **TensorFlow & Keras**
- Handles missing/irregular files gracefully

---

## 🗃️ Dataset

- Used the [VITON dataset](https://github.com/xthan/VITON) for person-cloth pairs
- Preprocessing:
  - Pose estimation using **MMPose**
  - Human parsing via [Robust Human Parsing](https://github.com/Engineering-Course/HRNet-Human-Pose-Estimation)
  - Generated **agnostic images** to guide the generator

---

## 🏗️ Pipeline Overview

```plaintext
Cloth Image
     │
     └──┐
        ▼
    Agnostic Image  ◄── Person Image ──┐
           │                          ▼
           └────►  Generator  ◄───── Cloth Image
                            │
                            ▼
                   Generated Try-On Image
