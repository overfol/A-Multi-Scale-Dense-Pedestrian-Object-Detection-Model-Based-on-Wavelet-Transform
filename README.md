# A Multi-Scale Dense Pedestrian Object Detection Model Based on Wavelet Transform

This repository provides the official implementation of the paper:

**A Multi-Scale Dense Pedestrian Object Detection Model Based on Wavelet Transform**

## 1. Introduction

Pedestrian detection in dense and complex scenes remains challenging due to severe occlusion, large-scale variation, and background interference. To address these issues, we propose a **multi-scale dense pedestrian object detection model based on wavelet transform**. The proposed method integrates wavelet-transform-based feature enhancement into the object detection framework to improve multi-scale feature representation and detection performance, especially for small and densely distributed pedestrians.

This repository is publicly released to support the **reproducibility** of the proposed method and to improve the **transparency and reliability** of the experimental results reported in the paper.

## 2. Highlights

- Wavelet-transform-based feature enhancement
- Improved performance for dense and multi-scale pedestrian detection
- Implemented based on the YOLOv8 framework
- Publicly released for academic reproducibility

## 3. Repository Structure

A recommended project structure is shown below:

```text
.
├── datasets/                  # Dataset directory
│   ├── images/
│   │   ├── train/
│   │   ├── val/
│   │   └── test/
│   ├── labels/
│   │   ├── train/
│   │   ├── val/
│   │   └── test/
│   └── data.yaml
├── models/                    # Model definitions or configuration files
├── weights/                   # Pretrained weights or trained checkpoints
├── train.py                   # Training script
├── val.py                     # Validation script
├── detect.py                  # Inference script
├── requirements.txt           # Python dependencies
└── README.md
```

> Note: Please modify this structure according to the actual files in your repository.

## 4. Environment

Recommended environment:

- Python 3.9 or higher
- PyTorch 2.0 or higher
- CUDA 11.8 or higher (if GPU is used)
- Ubuntu / Windows

### 4.1 Install Dependencies

If `requirements.txt` is provided, run:

```bash
pip install -r requirements.txt
```

If not, a typical environment can be installed with:

```bash
pip install torch torchvision torchaudio
pip install ultralytics opencv-python matplotlib numpy pandas pyyaml tqdm
```

## 5. Dataset Preparation

Please organize the dataset in YOLO format.

Example dataset structure:

```text
datasets/
├── images/
│   ├── train/
│   ├── val/
│   └── test/
├── labels/
│   ├── train/
│   ├── val/
│   └── test/
└── data.yaml
```

### 5.1 Example of `data.yaml`

```yaml
path: ./datasets
train: images/train
val: images/val
test: images/test

names:
  0: pedestrian
```

### 5.2 Dataset Used in This Work

Please clearly specify the dataset used in the paper, for example:

- WiderPerson
- CrowdHuman

    

## 6. Training

Run the following command to start training:

```bash
python train.py
```

If your training script supports parameterized input, you may also use a command like:

```bash
python train.py --data datasets/data.yaml --cfg your_model.yaml --weights pretrained.pt --img 640 --batch 16 --epochs 100
```

Please modify the command according to your actual implementation.

## 7. Validation

Run the following command to evaluate the model on the validation set:

```bash
python val.py
```

For example:

```bash
python val.py --weights weights/best.pt --data datasets/data.yaml --img 640
```

## 8. Inference

Run the following command for inference on images or videos:

```bash
python detect.py
```

For example:

```bash
python detect.py --weights weights/best.pt --source path/to/image_or_video
```

## 9. Main Experimental Settings

To improve reproducibility, please provide the key experimental settings used in the paper, such as:

- Input image size: `640 × 640`
- Batch size: `16`
- Number of epochs: `100`
- Optimizer: `SGD / Adam`
- Initial learning rate: `0.01 / 0.001`
- Hardware: `NVIDIA GPU`
- Framework: `PyTorch + YOLOv8`

> Please replace the above placeholders with the actual settings used in your experiments.

## 10. Reproducibility Notes

To reproduce the experimental results as closely as possible, users are recommended to:

1. Use the same dataset split as described in the paper;
2. Use the same training hyperparameters and settings;
3. Use the same input resolution and preprocessing pipeline;
4. Evaluate the model with the same metrics reported in the manuscript.

Due to differences in hardware, random seeds, and software versions, slight deviations from the reported numerical results may occur, but the overall trend should remain consistent.

## 11. Statement

This repository is released for academic research and experimental reproducibility purposes only. If this work is helpful to your research, please consider citing our paper.
