# ⚽ Abu Treika Detection with YOLOv8

> Object detection project to detect **Mohamed Abu Treika** — the legendary Egyptian
> footballer — using **YOLOv8** fine-tuned on a custom dataset.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-00FFFF)
![Roboflow](https://img.shields.io/badge/Roboflow-Dataset-blueviolet)
![OpenCV](https://img.shields.io/badge/OpenCV-green?logo=opencv&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)

---

## 📋 Table of Contents

- [The Problem](#-the-problem)
- [Approach](#-approach)
- [Results](#-results)
- [Setup](#-setup)
- [Usage](#-usage)
- [Tech Stack](#-tech-stack)

---

## 🎯 The Problem

The standard YOLOv8n model (trained on COCO) has no concept of *who* a person is — it
only detects "person" generically. This project fine-tunes YOLOv8 to specifically
recognize Abu Treika in images.

| Before Fine-Tuning | After Fine-Tuning |
|---|---|
| Detected as **person** ❌ | Detected as **Abu Treika** ✅ |

**Sample input:**

![Sample Input](assets/sample_input.png)

**Output after COCO inference (generic "person"):**

![Sample Output](assets/sample_output.png)

---

## 🧩 Approach

1. **Baseline** — Run pretrained `yolov8n.pt` (COCO) — detects "person" only.
2. **Dataset** — Collected and annotated Abu Treika images using [Roboflow](https://roboflow.com).
3. **Fine-tuning** — Trained YOLOv8n on the custom dataset with heavy augmentation.
4. **Evaluation** — Measured mAP50 and mAP50-95 on the validation set.
5. **Dual inference** — COCO model (blue) + fine-tuned model (green) side by side.

---

## 📊 Results

| Metric | Value |
|---|---|
| mAP50 | **0.747** |
| mAP50-95 | **0.529** |
| Recall | **1.000** |

> 📝 Note: the dataset is small (12 training images). Adding more images will
> significantly improve results.

---

## 🚀 Setup

```bash
git clone https://github.com/khaled-ghanem/AbuTreika-detection-yolov8.git
cd AbuTreika-detection-yolov8
python -m venv .venv
source .venv/bin/activate        # On Windows: .venv\Scripts\activate
pip install ultralytics roboflow
```

---

## 💻 Usage

Open `yolov8_inference.ipynb` and run the cells in order:

| Part | Description |
|---|---|
| Part 1 | Baseline inference with pretrained YOLOv8 (COCO) |
| Part 2 | Download custom dataset from Roboflow |
| Part 3 | Fine-tune on the Abu Treika dataset with augmentation |
| Part 4 | Compare COCO vs fine-tuned model side by side |

---

## 🛠️ Tech Stack

- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- [Roboflow](https://roboflow.com) — dataset annotation and augmentation
- OpenCV, Matplotlib

---

<p align="center"><i>From generic "person" to "Abu Treika" — fine-tuning in action. ⚽</i></p>
