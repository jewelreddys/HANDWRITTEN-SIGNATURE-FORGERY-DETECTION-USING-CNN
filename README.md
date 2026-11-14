# Handwritten Signature Forgery Detection Using CNN

A Deep Learning and Computer Vision project that identifies genuine and forged handwritten signatures using a Convolutional Neural Network (CNN).

**Project Domain:** Deep Learning | Computer Vision | Image Classification

**Institution:** Vellore Institute of Technology (VIT), India

**Programming Language:** Python

---

## 1. Project Overview

Handwritten signatures are commonly used for identity verification and authentication. However, distinguishing genuine signatures from forged ones can be challenging, particularly when signatures exhibit natural variations in handwriting.

This project develops a CNN-based image classification approach to distinguish genuine handwritten signatures from forged signatures.

The system processes signature images, performs image preprocessing, and trains a Convolutional Neural Network to learn visual patterns associated with genuine and forged signatures.

The trained model can classify signature images into two categories:

- **Genuine Signature:** An authentic handwritten signature.
- **Forged Signature:** A forged handwritten signature.

## 2. Key Features

- Signature image collection and preprocessing.
- Genuine and forged signature classification.
- Grayscale image processing.
- Image resizing to 256 × 256 pixels.
- CNN-based feature extraction and classification.
- Dropout and Batch Normalization for model regularization.
- Early Stopping to monitor validation loss.
- Training and validation performance visualization.
- Confusion matrix and classification report.
- Model saving and signature prediction.

## 3. Dataset Description

The project uses handwritten signature image collections organized into genuine and forged categories.

The notebook combines images from multiple dataset folders and a sample signature collection.

**Dataset categories:**

| Class | Label | Description |
|---|---:|---|
| Genuine | 0 | Authentic handwritten signatures |
| Forged | 1 | Forged handwritten signatures |

### Dataset Preprocessing

The following preprocessing operations are implemented:

1. Load signature images.
2. Convert images to grayscale.
3. Resize images to 256 × 256 pixels.
4. Replicate grayscale channels to obtain three-channel input.
5. Normalize pixel values to the range [0, 1].
6. Assign binary class labels.

### Dataset Splitting

The notebook first reserves approximately 1% of the collected data for inference. The remaining data is divided into training, validation and testing sets.

| Dataset | Number of images |
|---|---:|
| Training | 588 |
| Validation | 148 |
| Testing | 184 |

The dataset itself is not included in this repository. Users must configure the dataset paths according to their local directory structure.

## 4. Exploratory Data Analysis

Exploratory analysis is performed to understand signature image characteristics before model training.

The notebook examines:

- Genuine and forged signature samples.
- Distribution of genuine and forged images.
- RGB and grayscale image channels.
- Different image resizing dimensions.
- Image visibility and preprocessing requirements.

Grayscale images resized to 256 × 256 pixels are selected for model input.

## 5. CNN Model Architecture

The project implements a Sequential Convolutional Neural Network using TensorFlow and Keras.

### Architecture Overview

| Layer | Configuration |
|---|---|
| Input | 256 × 256 × 3 |
| Conv2D | 16 filters, 3 × 3, ReLU |
| MaxPooling2D | 3 × 3 |
| Dropout | 0.25 |
| Conv2D | 32 filters, 3 × 3, ReLU |
| MaxPooling2D | 2 × 2 |
| Dropout | 0.25 |
| Conv2D | 64 filters, 3 × 3, ReLU |
| MaxPooling2D | 2 × 2 |
| Dropout | 0.25 |
| Conv2D | 128 filters, 3 × 3, ReLU |
| MaxPooling2D | 2 × 2 |
| Dropout | 0.25 |
| Flatten | Feature transformation |
| Dense | 128 neurons, ReLU |
| BatchNormalization | Applied |
| Dropout | 0.25 |
| Output | 1 neuron, Sigmoid |

**Total parameters:** 1,146,785

### Model Configuration

- Optimizer: Adam
- Loss Function: Binary Crossentropy
- Evaluation Metric: Accuracy
- Batch Size: 32
- Maximum Epochs: 100
- Early Stopping: Patience of 10 epochs
- Best Weights: Restored using validation loss monitoring

## 6. Model Training and Evaluation

The model is trained using the training dataset and monitored against the validation dataset.

The notebook evaluates the model using:

- Training and validation accuracy.
- Training and validation loss.
- Testing accuracy.
- Confusion matrix.
- Precision, recall and F1-score.

### Recorded Model Performance

The following values are taken from the notebook's recorded evaluation output.

| Metric | Result |
|---|---:|
| Training Accuracy | 100% |
| Testing Accuracy | 95.7% |
| Test Samples | 184 |
| Class 0 Precision | 96% |
| Class 1 Precision | 96% |
| Class 0 Recall | 96% |
| Class 1 Recall | 96% |

The model achieved approximately 95.7% accuracy on the held-out test split.

The training accuracy is higher than the testing accuracy, indicating that further validation and generalization testing would be useful.

## 7. Signature Prediction

After training, the model is saved in HDF5 format as:

`signature_model.h5`

The notebook also implements a prediction function that accepts an image path and a trained model.

The prediction output is classified using a sigmoid probability threshold of 0.5:

- Prediction 0: Real Signature
- Prediction 1: Forged Signature

## 8. Technology Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Deep Learning | TensorFlow, Keras |
| Computer Vision | OpenCV |
| Data Processing | NumPy, Pandas |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Image Processing | Pillow |
| Development Environment | Jupyter Notebook |

## 9. Repository Structure

```text
HANDWRITTEN-SIGNATURE-FORGERY-DETECTION-USING-CNN/
│
├── README.md
├── Handwritten_Signature_Forgery_Detection.ipynb
├── requirements.txt
├── .gitignore
│
├── screenshots/
│   ├── genuine-signature.png
│   ├── forged-signature.png
│   ├── training-results.png
│   └── confusion-matrix.png
│
└── results/
    └── evaluation-results.png
```

The screenshots and results directories are intended for genuine figures captured from the notebook. They can be added as the corresponding images become available.

## 10. Getting Started

### Prerequisites

- Python 3.10
- Jupyter Notebook
- Signature image dataset
- Required Python dependencies

### Step 1: Clone the Repository

```bash
git clone https://github.com/jewelreddys/HANDWRITTEN-SIGNATURE-FORGERY-DETECTION-USING-CNN.git
```

### Step 2: Navigate to the Project

```bash
cd HANDWRITTEN-SIGNATURE-FORGERY-DETECTION-USING-CNN
```

### Step 3: Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it:

**Windows**

```bash
.venv\Scripts\activate
```

**macOS / Linux**

```bash
source .venv/bin/activate
```

### Step 4: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 5: Configure Dataset Paths

The original notebook uses local Windows directory paths.

Update the paths in the data-loading cells to match the location of your signature dataset.

### Step 6: Run the Notebook

```bash
jupyter notebook
```

Open `Handwritten_Signature_Forgery_Detection.ipynb` and execute the cells in sequence.

## 11. Future Enhancements

- Explore Siamese Neural Networks for signature similarity learning.
- Improve generalization across different handwriting styles.
- Develop a real-time signature verification interface.
- Integrate the trained model into a web application.
- Evaluate performance on independent signature datasets.
- Improve image preprocessing and prediction consistency.

## 12. Author

**S. Jewel Reddy**

Integrated M.Tech – Computer Science (Data Science)

Vellore Institute of Technology (VIT), India

[GitHub Profile](https://github.com/jewelreddys)

---

This project was developed as an academic exploration of deep learning and computer vision techniques for handwritten signature forgery detection.
