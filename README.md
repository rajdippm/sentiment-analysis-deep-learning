# 🎬 Sentiment Analysis using Deep Learning (CNN & LSTM)

Deep learning-based sentiment analysis on the **IMDB movie reviews dataset** using **CNN** and **LSTM** models.  
Includes preprocessing, training with callbacks, visualizations, evaluation, and **real-time text prediction**.

---

## 📌 Project Overview

This project performs **binary sentiment classification** (Positive / Negative) using two neural network architectures:

- **Convolutional Neural Network (CNN)**
- **Long Short-Term Memory Network (LSTM)**

Both models are implemented using **Keras (TensorFlow backend)** and follow a complete end-to-end workflow:
> dataset loading → preprocessing → padding → model building → training → evaluation → inference

---

## 📊 Dataset: IMDB Movie Reviews

- **50,000 labeled movie reviews**
- **25,000 training + 25,000 testing**
- Labels: **0 = Negative**, **1 = Positive**
- Loaded via `keras.datasets.imdb`
- Uses only the **top 20,000 most frequent words**

---

## 🧹 Preprocessing Steps

- Convert integer-encoded reviews back to text for verification  
- Analyze review lengths  
- Pad all reviews to the maximum review length  
- Vocabulary size: **20,000 words**

---

## 🧠 Model Architectures

### 📌 CNN Model
- Embedding Layer  
- 1D Convolution (Conv1D)  
- MaxPooling  
- GlobalMaxPooling  
- Dense Layers  
- Sigmoid Output  

➡️ **CNN learns local word patterns and n-grams effectively.**

---

### 📌 LSTM Model
- Embedding Layer  
- LSTM Layer (128 units)  
- Dense Layers + Dropout  
- Sigmoid Output  

➡️ **LSTM captures long-range dependencies and sentence structure.**

---

## ⚙️ Training Details

Both models are trained using:
- **Binary Crossentropy** loss  
- **Adam** optimizer  
- **Accuracy** as the evaluation metric  
- **Callbacks**:
  - ModelCheckpoint (saves best model)
  - EarlyStopping
  - ReduceLROnPlateau
  - TerminateOnNaN

---

## 📈 Model Performance

### 🔹 CNN Model Results
- **Training Accuracy:** 98.5%  
- **Validation Accuracy:** 90.6%  
- **Test Accuracy:** 89.7%

The CNN model generalizes well and captures strong local text features.

---

### 🔹 LSTM Model Results
- **Training Accuracy:** 97.8%  
- **Validation Accuracy:** 88.2%  
- **Test Accuracy:** 86.3%

The LSTM performs slightly lower due to more overfitting but still achieves strong results.

---

## 📊 Performance Comparison

| Model | Training Accuracy | Validation Accuracy | Test Accuracy |
|-------|-------------------|---------------------|---------------|
| **CNN**  | 98.5% | 90.6% | 89.7% |
| **LSTM** | 97.8% | 88.2% | 86.3% |

---

## 🔍 Interpretation

- **CNN outperforms LSTM** on validation and test accuracy → better generalization  
- Both models achieve **high training accuracy**, showing strong learning ability  
- CNN is often more effective for IMDB data due to capturing **short-range patterns**  

---

## 📌 Summary

- **CNN Model:** Best overall performance — strong generalization  
- **LSTM Model:** Slightly lower but effective for sequential text modeling  
