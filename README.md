# Potato Leaf Disease Detection using CNN

A machine learning project for classifying potato leaf diseases using Convolutional Neural Networks (CNN), with performance comparisons against Support Vector Machine (SVM) and Random Forest classifiers.

## Overview

Potato plants are susceptible to several diseases that can significantly reduce crop yield. Early detection is essential to minimize losses and improve agricultural productivity.

This project develops an image classification system capable of identifying potato leaf conditions from images into three categories:

- Potato___Early_blight
- Potato___Late_blight
- Potato___healthy

The primary model is a Convolutional Neural Network (CNN), while Support Vector Machine (SVM) and Random Forest are implemented as baseline comparison models.

## Team Members

| NRP | Name |
|------|------|
| 5025241135 | Farikh Muhammad Fauzan |
| 5025241138 | William Hans Chandra |
| 5025241140 | Brave Juliada |
| 5025241185 | Muhammad Nawfal Alfanni D |

## Dataset

Dataset: PlantVillage Dataset

Source:
https://www.kaggle.com/datasets/mohitsingh1804/plantvillage

### Potato Classes Used

| Class | Description |
|---------|-------------|
| Potato___Early_blight | Early Blight Disease |
| Potato___Late_blight | Late Blight Disease |
| Potato___healthy | Healthy Potato Leaf |

### Dataset Statistics

| Class | Number of Images |
|---------|----------------|
| Early Blight | 800 |
| Late Blight | 800 |
| Healthy | 121 |
| **Total** | **1721** |

### Data Split

- Training Set: 80%
- Validation Set: 20%

## Project Structure

```text
.
├── potatoleafdisease.ipynb
├── potatoleafdisease.py
├── plant_disease_cnn_model.keras
├── README.md
└── images/
    ├── training_accuracy.png
    ├── confusion_matrix.png
    └── prediction_examples.png
```

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-Learn
- KaggleHub

## Model Architecture

The CNN architecture consists of:

```text
Input Image (224x224x3)
        │
Rescaling Layer
        │
Conv2D (32 filters)
        │
MaxPooling2D
        │
Conv2D (64 filters)
        │
MaxPooling2D
        │
Conv2D (128 filters)
        │
MaxPooling2D
        │
Flatten
        │
Dense (128 neurons)
        │
Dropout (0.5)
        │
Dense (3 neurons, Softmax)
```

## Installation

### 1. Install Python

Download and install Python:

https://www.python.org/downloads/

Verify installation:

```bash
python --version
```

or

```bash
python3 --version
```

### 2. Clone Repository

```bash
git clone https://github.com/your-username/potato-leaf-disease-detection.git

cd potato-leaf-disease-detection
```

### 3. Create Virtual Environment (Recommended)

```bash
python -m venv venv
```

Activate:

Windows:

```bash
venv\Scripts\activate
```

Linux / macOS:

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install tensorflow
pip install numpy
pip install matplotlib
pip install scikit-learn
pip install kagglehub
pip install seaborn
```

Or:

```bash
pip install -r requirements.txt
```

## Running the Project

### Using Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
potatoleafdisease.ipynb
```

### Using Google Colab

1. Open Google Colab
2. Upload `potatoleafdisease.ipynb`
3. Run all cells sequentially

## Training Process

The model is trained using:

- Image Size: 224 × 224
- Batch Size: 32
- Optimizer: Adam
- Loss Function: Sparse Categorical Crossentropy
- Epochs: 10

## Results

### CNN Performance

| Metric | Value |
|----------|---------|
| Validation Accuracy | 93.9% |
| Validation Loss | 0.2319 |

### Model Comparison

| Model | Validation Accuracy |
|---------|------------------|
| CNN | 93.9% |
| SVM (Scenario 1) | 89.0% |
| Random Forest (Scenario 1) | 86.6% |
| SVM (Scenario 2) | 89.5% |
| Random Forest (Scenario 2) | 88.1% |

## Handling Class Imbalance

The dataset contains a significant imbalance:

- Early Blight: 800 images
- Late Blight: 800 images
- Healthy: 121 images

To address this issue, a second experiment was conducted using:

```python
class_weight='balanced'
```

for both SVM and Random Forest models.

## Evaluation Metrics

The project evaluates model performance using:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Confusion Matrix

## Disease Prediction

The notebook allows users to upload custom potato leaf images and obtain predictions.

Output example:

```text
Prediction: Potato___Late_blight
Confidence: 97.35%
```

## Example Workflow

```text
Input Image
      ↓
Preprocessing
      ↓
CNN Model
      ↓
Softmax Classification
      ↓
Disease Prediction
      ↓
Confidence Score
```

## Future Improvements

- Data augmentation
- Transfer learning (MobileNetV2, EfficientNet, ResNet)
- Hyperparameter tuning
- Larger potato disease dataset
- Deployment as a web application
- Real-time mobile inference

## Conclusion

The CNN model achieved the highest performance with a validation accuracy of 93.9%, outperforming traditional machine learning approaches such as SVM and Random Forest. The results demonstrate the effectiveness of deep learning for image-based potato leaf disease classification and highlight CNN's ability to automatically learn discriminative visual features from plant leaf images.

## License

This project was developed for educational purposes as part of a Machine Learning Final Project.
