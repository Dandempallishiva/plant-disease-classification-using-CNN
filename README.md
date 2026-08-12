# 🌿 Plant Disease Classification Using CNN

## 📌 Project Overview

This project implements a **Convolutional Neural Network (CNN)** to classify plant leaf images into different plant disease categories.

The model is trained using the **New Plant Diseases Dataset (Augmented)** and performs multi-class image classification using **TensorFlow and Keras**.

The project covers the complete deep learning workflow:

**Image Dataset → Preprocessing → CNN → Training → Validation → Prediction**

---

## 🎯 Objectives

* Build a CNN-based image classification model.
* Classify plant leaves into their respective disease categories.
* Prepare and preprocess image datasets for deep learning.
* Train and validate a multi-class CNN model.
* Analyze training and validation performance.
* Use the trained model to predict the disease of a new plant leaf image.

---

## 📊 Dataset

The project uses the **New Plant Diseases Dataset (Augmented)**.

| Dataset         | Images | Classes |
| --------------- | -----: | ------: |
| Training        | 70,295 |      38 |
| Validation/Test | 17,572 |      38 |

The images are loaded using TensorFlow's `image_dataset_from_directory()`.

Each directory corresponds to a different plant disease class.

---

## 🖼️ Image Preprocessing

The input images are resized to:

```text
128 × 128 × 3
```

where:

* `128` → image height
* `128` → image width
* `3` → RGB color channels

The dataset is processed using a batch size of:

```text
16
```

Images are normalized before being passed to the model.

---

## 🧠 CNN Architecture

The project uses a custom Convolutional Neural Network.

```text
Input Image
     ↓
Conv2D (16 filters, 3×3, ReLU)
     ↓
MaxPooling2D
     ↓
Conv2D (32 filters, 3×3, ReLU)
     ↓
MaxPooling2D
     ↓
Conv2D (64 filters, 3×3, ReLU)
     ↓
MaxPooling2D
     ↓
Flatten
     ↓
Dropout (0.2)
     ↓
Dense (128 neurons, ReLU)
     ↓
Dense (38 neurons)
     ↓
Plant Disease Class
```

### CNN Components

**Convolutional Layers**

Extract visual features such as edges, textures, shapes, and disease-related patterns from plant leaves.

**Max Pooling**

Reduces the spatial dimensions of the feature maps while retaining important features.

**Flatten**

Converts the extracted feature maps into a one-dimensional vector.

**Dropout**

A dropout rate of `0.2` is used to reduce overfitting.

**Dense Layer**

The 128-neuron dense layer learns higher-level representations from the extracted image features.

**Output Layer**

The final layer contains **38 neurons**, corresponding to the 38 plant disease classes.

---

## ⚙️ Model Configuration

| Parameter          | Value                           |
| ------------------ | ------------------------------- |
| Model              | Convolutional Neural Network    |
| Input Size         | 128 × 128 × 3                   |
| Batch Size         | 16                              |
| Optimizer          | Adam                            |
| Loss Function      | Sparse Categorical Crossentropy |
| Loss Configuration | `from_logits=True`              |
| Dropout            | 0.2                             |
| Hidden Dense Layer | 128 neurons                     |
| Output Classes     | 38                              |
| Epochs             | 10                              |
| Evaluation Metric  | Accuracy                        |

---

## 📈 Training Results

The model was trained for **10 epochs**.

### Final Training Performance

* **Training Accuracy:** 97.50%
* **Training Loss:** 0.0807
* **Validation Accuracy:** 94.64%
* **Validation Loss:** 0.2245

The model achieved its highest recorded validation accuracy of approximately **94.64%** at the end of the 10th epoch.

---

## 📊 Training & Validation Analysis

The training history tracks:

* Training Accuracy
* Validation Accuracy
* Training Loss
* Validation Loss

These metrics can be visualized to understand how the CNN learns over the training epochs and how well it generalizes to validation data.

---

## 🔎 Prediction on a New Leaf Image

The trained CNN was also used to classify an individual plant leaf image.

### Prediction Pipeline

```text
Input Leaf Image
       ↓
Resize to 128 × 128
       ↓
Convert to NumPy Array
       ↓
Normalize Pixel Values
       ↓
Add Batch Dimension
       ↓
CNN Prediction
       ↓
Find Highest-Scoring Class
       ↓
Predicted Disease
```

### Example Prediction

The model predicted:

```text
Squash___Powdery_mildew
```

for the tested leaf image.

---

## 🔄 End-to-End Workflow

```text
New Plant Disease Dataset
          ↓
Load Images
          ↓
Resize Images
          ↓
Create Training & Validation Datasets
          ↓
Normalize Images
          ↓
CNN Feature Extraction
          ↓
Max Pooling
          ↓
Flatten
          ↓
Dense Layer
          ↓
Disease Classification
          ↓
Model Evaluation
          ↓
New Image Prediction
```

---

## 🛠️ Technologies Used

* **Python**
* **TensorFlow**
* **Keras**
* **NumPy**
* **Pandas**
* **Matplotlib**
* **Jupyter Notebook / Google Colab**

---

## 📁 Project Structure

```text
plant-disease-using-cnn/
│
├── plant_disease_using_CNN.ipynb
├── README.md
├── requirements.txt
│
└── images/
    ├── sample_images.png
    ├── training_validation_accuracy.png
    └── training_validation_loss.png
```

---

## 💡 Key Learning Outcomes

Through this project, I gained practical experience with:

* Image classification
* Convolutional Neural Networks
* Image preprocessing
* TensorFlow image datasets
* Convolution layers
* Max pooling
* Feature extraction
* Flattening
* Dropout regularization
* Dense neural networks
* Multi-class classification
* ReLU activation
* Adam optimization
* Sparse categorical crossentropy
* Training and validation analysis
* Single-image prediction

---

## 🚀 Future Improvements

* Apply advanced data augmentation techniques.
* Experiment with transfer learning using **VGG16, ResNet, or MobileNet**.
* Add confusion matrix and class-wise evaluation.
* Improve performance on visually similar diseases.
* Build a web application for real-time plant disease prediction.
* Deploy the trained model as an API or mobile application.

---

## 👨‍💻 Author

**Shiva**

B.Tech – Artificial Intelligence & Machine Learning
