# Pneumonia Detection using CNN

This project explores the use of Convolutional Neural Networks (CNNs) to classify chest X-ray images as either **Pneumonia** or **Normal**. Two versions of the model were built and compared:

- 📄 Initial Model – A baseline CNN with minimal layers.
- ⚡ Optimized Model – An improved CNN with regularization and deeper architecture.

---

## 🛠️ Initial Model

The initial model is a simple CNN designed as a baseline.

**Architecture**
- `Conv2D(32)` + `MaxPooling2D`
- `Conv2D(64)` + `MaxPooling2D`
- `Flatten`
- `Dense(64)`
- `Dense(1, sigmoid)`

**Key Characteristics**
- No normalization layers
- No dropout layers
- Smaller dense layer (64 units)
- Focused mainly on establishing a working baseline

---

## 🚀 Optimized Model

The optimized model introduces architectural and training improvements.

**Architecture**
- `Conv2D(32)` + `MaxPooling2D` + `BatchNormalization`
- `Conv2D(64)` + `MaxPooling2D` + `BatchNormalization`
- `Conv2D(128)` + `MaxPooling2D` + `BatchNormalization`
- `Flatten`
- `Dense(128)` + `Dropout(0.5)`
- `Dense(1, sigmoid)`

**Training Improvements**
- Added **Batch Normalization** → stabilizes learning and improves convergence.
- Added **Dropout (0.5)** → reduces overfitting by randomly disabling neurons.
- Increased depth with an additional `Conv2D(128)` layer.
- Early stopping callback → prevents overfitting and reduces wasted training epochs.

---

## 📊 Results

| Model            | Accuracy | Loss  |
|------------------|----------|-------|
| 📄 Initial Model | 71.15%   | 3.02  |
| ⚡ Optimized Model | 83.33%   | 0.84  |

The optimized model clearly outperforms the initial baseline, achieving **higher accuracy** and **lower loss**, demonstrating better generalization on test data.

---

## 📂 Project Structure

- `Assignment3_CNN_s1053601.ipynb` – Main notebook containing data preprocessing, model building, training, and evaluation.
- `README.md` – Project documentation (this file).
