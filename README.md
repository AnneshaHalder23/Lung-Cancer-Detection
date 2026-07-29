# CentralGraphFormer for Lung Cancer CT Classification

This repository contains the implementation of **CentralGraphFormer**, a deep learning model for classifying lung CT images into **Benign**, **Malignant**, and **Normal** classes using the **IQ-OTH/NCCD Lung Cancer Dataset**. The work adapts the CentralGraphFormer architecture, originally proposed for hyperspectral image classification, to medical image analysis by incorporating graph attention and center-guided feature learning. :contentReference[oaicite:0]{index=0}

---

## Project Overview

Lung cancer is one of the leading causes of cancer-related deaths worldwide. Early diagnosis through CT imaging can improve treatment outcomes, but manual interpretation requires significant time and expertise.

The objective of this project is to develop a lightweight deep learning model capable of automatically classifying lung CT images into three categories:

- Benign
- Malignant
- Normal

The proposed model combines convolutional feature extraction with graph-based attention to learn both local and global representations from CT images.

---

## Dataset

**Dataset:** IQ-OTH/NCCD Lung Cancer Dataset

The dataset consists of CT scan images collected from patients and categorized into three classes.

| Class | Description |
|--------|-------------|
| Benign | Non-cancerous lung nodules |
| Malignant | Cancerous lung nodules |
| Normal | Healthy lungs |

### Dataset Summary

- Total Images: 1,328
- Number of Classes: 3
- Image Type: CT Scan Images

**Note:** The dataset is not included in this repository. Please download it from the official source and place it in the appropriate directory before running the project.

---

## Model Architecture

The proposed architecture consists of four main components:

- Spectral Shift Separable Network (S³-Net)
- Convolutional Block Attention Module (CBAM)
- Stochastic Dynamic Gating with Biological Vision Blurring (SDG+BVB)
- Central Graph Attention Module (CGAM)

These modules work together to extract discriminative features while modelling long-range relationships through graph attention. :contentReference[oaicite:1]{index=1}

---

## Project Structure

```
CentralGraphFormer-Lung-Cancer/
│
├── notebooks/
│   ├── CentralGraphFormer_Novel_Final.ipynb
│   ├── Unified_Feature_Extraction.ipynb
│   └── Compare_All_Features_with_MLP.ipynb
│
├── dataset/
├── models/
├── results/
├── README.md
└── requirements.txt
```

---

## Training Configuration

| Parameter | Value |
|-----------|-------|
| Optimizer | AdamW |
| Learning Rate | 0.0001 |
| Batch Size | 32 |
| Maximum Epochs | 200 |
| Loss Function | Class-Weighted Cross Entropy |
| Scheduler | ReduceLROnPlateau |
| Mixed Precision Training | Enabled |
| Gradient Clipping | Enabled |

---

## Results

The model achieved the following performance on the IQ-OTH/NCCD dataset:

| Metric | Value |
|--------|-------|
| Overall Accuracy | **90.87%** |
| Average Accuracy | **64.07%** |
| Cohen's Kappa | **0.824** |

The model performed well on the malignant and normal classes but struggled with the minority benign class because of the severe class imbalance present in the dataset. :contentReference[oaicite:2]{index=2}

---

## Evaluation Metrics

The following evaluation metrics were used:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- Classification Report
- Cohen's Kappa

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/CentralGraphFormer-Lung-Cancer.git
```

Move into the project directory:

```bash
cd CentralGraphFormer-Lung-Cancer
```

Install the required packages:

```bash
pip install -r requirements.txt
```

---

## Running the Project

Open the notebook

```
CentralGraphFormer_Novel_Final.ipynb
```

Run all cells sequentially.

If a training script is available, it can be executed using:

```bash
python train.py
```

---

## Future Work

Some possible improvements include:

- Addressing class imbalance using focal loss or oversampling techniques
- Cross-validation for more reliable evaluation
- Testing on additional lung CT datasets
- Hyperparameter optimisation
- Explainability using Grad-CAM or attention visualisation
- Deployment as a web application

---

## Technologies Used

- Python
- PyTorch
- NumPy
- Pandas
- OpenCV
- Scikit-learn
- Matplotlib
- Google Colab

---

## Citation

If you use this work in your research, please cite:

```bibtex
@article{halder2026centralgraphformer,
  title={CentralGraphFormer for Lung Cancer CT Classification},
  author={Annesha Halder and Kshitij Mishra and Maloy Dey and Dushmanta Kumar Das},
  year={2026}
}
```

---

## Author

**Annesha Halder**

B.Tech Student

Research Interests:
- Deep Learning
- Medical Image Analysis
- Computer Vision
- Artificial Intelligence

---

## License

This project is intended for research and educational purposes only.

Please follow the licensing terms of the IQ-OTH/NCCD dataset when using the data.
