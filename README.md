# yolo-solid-waste-detection
Solid Waste Detection in Diverse Environments using YOLOv11 and YOLOv12 Models'.
# Solid Waste Detection using YOLOv11 and YOLOv12

This repository contains the official source code, configuration files, and trained models for the research paper: **"Solid Waste Detection in Diverse Environments using YOLOv11 and YOLOv12 Models"**.

Our work provides a comparative analysis of YOLOv11 and YOLOv12 for the challenging task of automated solid waste detection, establishing new performance benchmarks.

[![Paper](https://img.shields.io/badge/Paper-Link-blue)](https://link-to-your-paper.com)  <-- *Replace with the actual link once you have it*

---

## Table of Contents
- [Project Overview](#project-overview)
- [Setup and Installation](#setup-and-installation)
- [Dataset](#dataset)
- [Training](#training)
- [Evaluation](#evaluation)
- [Inference](#inference)
- [Results](#results)
- [Citation](#citation)

---

## Project Overview

This project aims to:
1.  Compare the performance of YOLOv11 and YOLOv12 on a diverse solid waste dataset.
2.  Analyze the trade-offs between accuracy and inference efficiency.
3.  Provide reproducible benchmarks for future research in environmental AI.

## Setup and Installation

Follow these steps to set up the environment and run the code.

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone https://github.com/your-username/yolo-solid-waste-detection.git
cd yolo-solid-waste-detection


2. Set up a Virtual Environment (Recommended)

python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

3. Install Dependencies

Install all required Python packages using the requirements.txt file:

pip install -r requirements.txt

Dataset

The dataset used for this study is sourced from the Roboflow Universe platform. It contains 4,404 images across multiple waste categories.

    Link to Dataset: https://universe.roboflow.com/kodiworkspace/solidwaste-l3nln/dataset/2
The dataset structure is defined in the data/data.yaml file, which is configured for use with the Ultralytics YOLO framework.
Training

The models were trained for 20 epochs on an NVIDIA Tesla T4 GPU. The hyperparameters are detailed in our paper.

To re-train a model, you can use the Ultralytics command-line interface. For example, to train YOLOv12:
yolo train model=yolov12.yaml data=data/data.yaml epochs=20 imgsz=640 batch=16

Evaluation

To evaluate the final performance of a trained model on the validation set, use the following command. This will generate the mAP, precision, and recall metrics reported in the paper.
yolo val model=weights/yolov12_best.pt data=data/data.yaml imgsz=640

Inference

To run inference on a new image or video, use the detect mode.

yolo detect model=weights/yolov12_best.pt source=path/to/your/image.jpg

The results will be saved in the runs/detect/ directory.
On a Video
yolo detect model=weights/yolov12_best.pt source=path/to/your/video.mp4

Results

Our experiments show that YOLOv12 outperforms YOLOv11 for this task, achieving a higher mAP and recall.
Model	mAP@0.5:0.95	Precision	Recall	Latency (ms)
YOLOv11	68.3%	0.896	0.748	11.2
YOLOv12	70.7%	0.895	0.771	15.9

For a detailed breakdown of per-category performance and a full discussion of these results, please refer to our paper.
Citation

If you find this work useful for your research, please consider citing our paper:


    
