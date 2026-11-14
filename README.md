# Handwritten Signature Forgery Detection Using CNN

A Deep Learning-based system for detecting forged handwritten signatures using Convolutional Neural Networks (CNN) and computer vision techniques.

## Project Overview

Handwritten signatures are widely used for identity verification and authentication. However, forged signatures can create security and verification challenges.

This project explores an automated approach to signature forgery detection using image processing and deep learning. The model analyzes handwritten signature images and learns visual patterns that help distinguish genuine signatures from forged ones.

## Key Features

- Handwritten signature image processing.
- Image preprocessing and preparation.
- CNN-based deep learning model.
- Training and validation workflow.
- Signature classification and forgery detection.
- Model performance evaluation.

## Technology Stack

| Category | Technologies |
|---|---|
| Programming | Python |
| Deep Learning | TensorFlow, Keras |
| Computer Vision | OpenCV |
| Data Processing | NumPy, Pandas |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Development | Jupyter Notebook |

## Project Workflow

1. Load handwritten signature images.
2. Preprocess and prepare image data.
3. Split the dataset into training and testing sets.
4. Train the CNN model.
5. Evaluate model performance.
6. Predict whether signatures are genuine or forged.

## Model Architecture

The project uses a Convolutional Neural Network to learn image features relevant to signature classification.

The exact layer configuration and training parameters are documented in the Jupyter Notebook.

## Repository Structure

```text
HANDWRITTEN-SIGNATURE-FORGERY-DETECTION-USING-CNN/
│
├── README.md
├── Handwritten_Signature_Forgery_Detection.ipynb
├── requirements.txt
├── .gitignore
├── screenshots/
└── results/
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/jewelreddys/HANDWRITTEN-SIGNATURE-FORGERY-DETECTION-USING-CNN.git
```

### 2. Navigate to the project

```bash
cd HANDWRITTEN-SIGNATURE-FORGERY-DETECTION-USING-CNN
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the notebook

Open the notebook using Jupyter Notebook or Google Colab and execute the cells in sequence.

## Evaluation

The model evaluation section covers the performance of the trained CNN model. Evaluation metrics and results should be reported based on the actual notebook execution.

## Future Enhancements

- Improve generalization across different handwriting styles.
- Explore Siamese neural networks for signature similarity learning.
- Develop a real-time signature verification interface.
- Integrate the trained model into a web application.

## Author

**S. Jewel Reddy**

Integrated M.Tech – Computer Science (Data Science)  
Vellore Institute of Technology (VIT), India

[GitHub Profile](https://github.com/jewelreddys)

---

This repository is an academic deep learning project exploring handwritten signature verification and forgery detection using computer vision techniques.
