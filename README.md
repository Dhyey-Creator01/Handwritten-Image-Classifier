# 🧠 Handwritten Digit Classifier using CNN (MNIST)

This project implements a Convolutional Neural Network (CNN) using TensorFlow and Keras to classify handwritten digits from the popular MNIST dataset. The model achieves **~98.4% test accuracy**, and is capable of predicting digits from custom images.

> 🔍 Try uploading your own digit image (like `testnum.jpg`) and see the model predict it!

---

## 📌 Project Highlights

- ✅ CNN built with TensorFlow/Keras  
- ✅ Trained on MNIST dataset (28×28 grayscale digits)  
- ✅ Preprocessed custom image input support  
- ✅ 98%+ accuracy with minimal model  
- ✅ Written in Jupyter Notebook (easily editable and testable)  

---

## 🗂️ Dataset: MNIST

- 60,000 training images, 10,000 testing images  
- Each image: 28×28 grayscale  
- Preloaded via `tensorflow.keras.datasets`

---

## ⚙️ Preprocessing Steps

To prepare data for the CNN, we apply:

| Step             | Description                                                |
|------------------|------------------------------------------------------------|
| Reshape          | Add channel dimension → `(num_samples, 28, 28, 1)`         |
| Type Conversion  | Convert pixels to `float32`                                |
| Normalization    | Scale pixel values from `[0, 255]` to `[0, 1]` using `/ 255` |

**Why Normalize?**  
- CNNs train better with bounded inputs  
- Division by 255 is a fast form of min-max normalization  
- Maintains brightness/contrast while speeding up convergence  

---

## 🧠 Model Architecture

Built using the Keras `Sequential` API:

- **Input**: `(28, 28, 1)`  
- **Conv2D(32, 3×3, ReLU)**: learns spatial features (edges, curves)  
- **MaxPooling2D(2×2)**: downsamples feature maps  
- **Flatten**: converts 2D features to 1D  
- **Dense(64, ReLU)**: learns higher-level patterns  
- **Dropout(0.2)**: prevents overfitting  
- **Dense(10, Softmax)**: outputs class probabilities for digits 0–9  

---

## 🏋️ Model Training & Evaluation

- **Optimizer**: Adam  
- **Loss**: Sparse Categorical Crossentropy  
- **Epochs**: 20  
- **Test Accuracy**: ~98.4%

---

## 🔍 Predicting Custom Images

Custom digit images may vary in size, background, and format. We apply:

1. **Grayscale conversion & resize** to 28×28  
2. **Auto-inversion** if background is light  
3. **Normalization** to [0, 1]  
4. **Reshape** to `(1, 28, 28, 1)`

Then feed into the model to obtain a predicted digit.

---

## 📁 Project Structure

