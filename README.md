# sentiment-analysis-deep-learning
Deep learning-based sentiment analysis on the IMDB dataset using CNN and LSTM models. Includes preprocessing, training with callbacks, visualizations, evaluation, and real-time text prediction.

# 🎬 IMDB Movie Review Sentiment Analysis (CNN & LSTM)

This project performs **binary sentiment analysis** (Positive/Negative) on the **IMDB Movie Reviews dataset** using two deep-learning models:

- **Convolutional Neural Network (CNN)**
- **Long Short-Term Memory Network (LSTM)**

Both models are built using **Keras (TensorFlow backend)** and follow a complete pipeline:  
dataset loading → preprocessing → padding → model building → training → evaluation → inference.

---

## 📊 Dataset: IMDB Movie Reviews

- 50,000 labeled movie reviews  
- 25,000 training + 25,000 testing  
- Labels: **0 = Negative**, **1 = Positive**  
- Loaded directly from `keras.datasets.imdb`  
- Only top 20,000 most frequent words are used (`num_words=20000`)

---

## 🧹 Preprocessing Steps

- Convert integer sequences back to text for verification  
- Analyze review lengths  
- Pad all reviews to the **max review length**
- Vocabulary size = **20,000**

---

## 🧠 Model Architectures

### **📌 CNN Model**
- Embedding Layer  
- 1D Convolution (Conv1D)  
- MaxPooling  
- GlobalMaxPooling  
- Dense layers  
- Sigmoid output  

CNN learns **local word patterns and n-gram features**.

---

### **📌 LSTM Model**
- Embedding Layer  
- LSTM layer (128 units)  
- Dense layers + Dropout  
- Sigmoid output  

LSTM learns **long-range dependencies and sentence structure**.

---

## ⚙️ Training Details

Both models use:

- **Binary Crossentropy** loss  
- **Adam** optimizer  
- **Accuracy** as evaluation metric  
- **Callbacks:**  
  - ModelCheckpoint (save best model)  
  - EarlyStopping  
  - ReduceLROnPlateau  
  - TerminateOnNaN  

---

### 🔹 **CNN Model Results**
- **Training Accuracy:** 98.5%
- **Validation Accuracy:** 90.6%
- **Test Accuracy:** 89.7%

The CNN model generalizes well and demonstrates strong capability in capturing local text patterns (n-grams).

---

### 🔹 **LSTM Model Results**
- **Training Accuracy:** 97.8%
- **Validation Accuracy:** 88.2%
- **Test Accuracy:** 86.3%

The LSTM model performs slightly lower due to modeling long sequences, which can introduce higher overfitting. Still, it achieves strong predictive performance.

---

### 📊 **Performance Comparison**

| Model | Training Accuracy | Validation Accuracy | Test Accuracy |
|-------|-------------------|---------------------|---------------|
| **CNN**  | **98.5%**      | **90.6%**           | **89.7%**     |
| **LSTM** | **97.8%**      | **88.2%**           | **86.3%**     |

---

### 🔍 Interpretation

- **CNN outperforms LSTM** on validation and test accuracy, indicating better generalization for this dataset.
- Both models achieve high training accuracy, showing strong learning capability.
- CNN is typically more effective on IMDB due to capturing short-range text patterns, which aligns with these results.

---

### 📌 Summary
> **CNN Model:** Best overall performance — strong generalization  
> **LSTM Model:** Slightly lower but still excellent performance with good sequential understanding  

