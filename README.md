# Bottle Object Detection Project using YOLOv8
## Project Overview

This project focuses on building, training, and evaluating object detection models using the YOLOv8 architecture. The goal is to compare different YOLOv8 variants (n, s, m) in terms of accuracy, speed, and model size, and determine the most suitable model for deployment.

The dataset used is specific to the project, and fine-tuned models are evaluated to determine the best-performing variant.

## Repository Structure
```
YOLOv8-Object-Detection/
│
├── data/
│   └── dataset/               # Dataset files (images + annotations)
│
├── notebooks/
│   ├── YOLOv8n_object_detection.ipynb
│   
│   
│
├── results/
│   ├── comparison_table.xlsx  # Model performance comparison
│   ├── screenshots/           # Detection output screenshots
│   └── logs/                  # Training logs for reference
│
├── scripts/
│   ├── inference.py           # Run inference on new images/videos
│   └── evaluation.py          # Compute metrics for models
│
├── README.md                  # Project documentation
└── requirements.txt           # Python dependencies
```

## Models Compared
| Model   | mAP50 | mAP50–95 | Precision | Recall | Speed (ms) | Size (MB) |
| ------- | ----- | -------- | --------- | ------ | ---------- | --------- |
| YOLOv8n |       |          |           |        |            |           |
| YOLOv8s |       |          |           |        |            |           |
| YOLOv8m |       |          |           |        |            |           |

## Training Process

**1. Dataset Loading**

Dataset was uploaded and structured in YOLO format (images + .yaml annotations).

Used Roboflow to prepare and augment the dataset.

**2. Model Training**

Trained YOLOv8n, YOLOv8s, and YOLOv8m variants.

Monitored training metrics including loss, precision, recall, and mAP.

Saved model weights after training completion.

**3. Validation**

Each model was validated using a held-out validation set.

Metrics recorded: mAP50, mAP50–95, Precision, Recall, Inference Speed, and Model Size.

## Metrics Analysis

* Precision vs Recall:
Precision measures the proportion of correct positive detections, while recall measures how many true objects are detected.

* Performance Trade-offs:

  * Smaller models (YOLOv8n) are faster but may have slightly lower accuracy.

  * Larger models (YOLOv8m) tend to achieve higher accuracy but require more resources and have slower inference.

* Observations:

  * Identify which model performed best for accuracy.

  * Identify which model is more suitable for real-time applications based on speed vs accuracy trade-off.

## Inference Results

* Screenshots of detection outputs are included in results/screenshots/.

* Inference can be reproduced using scripts/inference.py.

## How to Reproduce
1.Clone the repository:
```
git clone https://github.com/<your_username>/YOLOv8-Object-Detection.git
cd YOLOv8-Object-Detection
```
2.Install dependencies:
```
pip install -r requirements.txt
```
3. Run training notebooks in ```notebooks/ to train the models.```

4. Evaluate models using ```scripts/evaluation.py ```or check the ```results/comparison_table.xlsx.```

5. Run inference on images:
```
python scripts/inference.py --image path/to/image.jpg --model path/to/best_model.pt
```
## Deliverables

1. Training Notebooks: Demonstrating dataset loading, training, and validation.

2. Comparison Table: Complete performance metrics across YOLOv8 variants.

3. Metrics Analysis: Insights on precision, recall, speed, and accuracy trade-offs.

4. Inference Outputs: Screenshots of predictions and optional real-time demo (bonus).

## Future Work

* Real-time deployment using a webcam or local video.

* Further fine-tuning for higher accuracy.

* Deploying the best model on edge devices for low-latency applications.

## License

This project is for academic purposes. For any usage, please cite this repository.
