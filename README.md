# Enhanced Multi-Scale Attention Framework for Retinal Vessel Segmentation

## Overview

This project focuses on retinal blood vessel segmentation using deep learning and computer vision. It implements a custom PyTorch architecture, **LMFRNet_V2**, designed to segment blood vessels from retinal fundus images while preserving fine vessel structures.

The framework combines multi-scale feature extraction, attention mechanisms, residual connections, and contrast enhancement to improve vessel representation and segmentation quality.

## Objectives

- Segment retinal blood vessels from fundus images.
- Extract features from vessels of different widths using multi-scale convolutions.
- Preserve thin vessels and spatial information through residual and skip connections.
- Improve image contrast through CLAHE preprocessing.
- Evaluate segmentation performance using multiple metrics.

## Key Features

- **Multi-Scale Convolution:** Uses parallel 1×1, 3×3, 5×5, and 7×7 convolutional kernels.
- **Attention Gates:** Emphasize relevant vessel features and suppress background information.
- **Residual Connections:** Support feature learning and information preservation.
- **CLAHE Preprocessing:** Enhances local contrast in retinal images.
- **Data Augmentation:** Uses horizontal flipping to improve training diversity.
- **Combined Loss Function:** Integrates Binary Cross-Entropy (BCE) Loss and Dice Loss.
- **AdamW Optimizer:** Optimizes network parameters during training.

## Dataset

The implementation focuses on the **DRIVE retinal vessel segmentation dataset**, which contains 40 retinal images, conventionally divided into 20 training and 20 testing images.

Images are resized to 512 × 512 pixels for model processing. The network generates vessel segmentation masks that distinguish blood vessel pixels from the background.

**Note:** The dataset is not included in this repository. Obtain it from the official dataset source and configure the dataset paths in the notebook before running the project.

## Model Architecture

LMFRNet_V2 follows an encoder-decoder architecture incorporating:

1. Multi-scale residual convolution blocks.
2. Attention gates on encoder skip features.
3. Decoder blocks for feature reconstruction.
4. A final convolutional layer for pixel-wise vessel prediction.
5. Sigmoid activation and thresholding to generate binary segmentation masks.

## Evaluation Metrics

The project considers the following metrics for segmentation evaluation:

| Metric | Purpose |
|---|---|
| Accuracy (ACC) | Measures overall pixel classification accuracy |
| Dice Score | Measures overlap between predicted and ground-truth masks |
| Intersection over Union (IoU) | Measures segmentation overlap |
| Sensitivity | Measures the detection of vessel pixels |
| Specificity | Measures the identification of background pixels |
| AUC | Evaluates discrimination across classification thresholds |
| MCC | Measures the quality of binary classification |
| clDice | Evaluates vessel connectivity and topology |
| HD95 | Measures boundary distance using the 95th percentile |

For reliable reporting, evaluate the trained model on an independent test set and compare it with baseline methods under consistent conditions.

## Technologies Used

- Python
- PyTorch
- OpenCV
- NumPy
- Albumentations
- Matplotlib
- Jupyter Notebook / Kaggle

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/abhinav28ai/Enhance-multi-scale-attention-framework-for-retinal-vessel-segmentation.git
cd Enhance-multi-scale-attention-framework-for-retinal-vessel-segmentation
```

### 2. Install dependencies

Create a virtual environment if required, then install the libraries used by the notebook:

```bash
pip install torch torchvision opencv-python numpy albumentations matplotlib scikit-learn
```

Install any additional packages required by your notebook.

### 3. Configure the dataset

Download the DRIVE dataset and update the image and mask paths in the notebook to match your local directory structure.

### 4. Run the notebook

Open the project notebook in Jupyter Notebook or upload it to Kaggle. Configure the dataset paths, select an appropriate compute environment, and execute the cells in order.

## Applications

- Retinal vessel structure analysis.
- Medical image segmentation research.
- Retinal image processing and visualization.
- Research on multi-scale attention-based segmentation networks.

**Disclaimer:** This project is intended for research and educational purposes. It is not a standalone medical diagnostic system.

## Future Improvements

- Improve detection of extremely thin vessels.
- Evaluate generalization across additional retinal datasets.
- Compare performance with established segmentation architectures.
- Optimize computational efficiency and inference speed.
- Add reproducible training, checkpoint saving, and independent test evaluation.

## Author

**Abhinav Pandey**

GitHub: [@abhinav28ai](https://github.com/abhinav28ai)

## License

A license has not yet been specified. Add a suitable license file if you intend to distribute or reuse this project publicly.
