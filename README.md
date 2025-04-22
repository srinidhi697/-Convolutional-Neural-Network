# 🧠 Convolutional Neural Network on CIFAR-10 and MNIST

This project explores the performance of **Convolutional Neural Networks (CNNs)** on two popular datasets: **CIFAR-10** and **MNIST**, with a focus on model design, training, evaluation, and performance improvement through deeper architectures.

---

## 📁 Project Structure

### 🔹 Part IV: CNN on CIFAR-10
- **Input**: 32x32x3 color images across 10 classes
- **Architecture**:
  - Conv1: 32 filters, 5x5, ReLU + MaxPool (2x2)
  - Conv2: 64 filters, 5x5, ReLU + MaxPool (2x2)
  - Flatten → Dense(1024) → Dropout(0.5) → Dense(10)
- **Training**:
  - Steps: 5000
  - Batch Size: 100
  - Optimizer: Adam
  - Dropout: 0.5

### 📈 CIFAR-10 Accuracy Over Time
| Step | Accuracy |
|------|----------|
| 0    | 10.83%   |
| 500  | 52.42%   |
| 1500 | 62.37%   |
| 3000 | 64.11%   |
| 4500 | **68.25%** (Peak) |
| 5000 | 66.45%   |

> Accuracy peaked at 68.25% at step 4500. Slight drop afterward suggests early signs of overfitting.

---

### 🔹 Part V: Comparison – CIFAR-10 vs MNIST

| Dataset   | Steps | Max Accuracy | Notes |
|-----------|-------|--------------|-------|
| MNIST     | 5000  | **99.21%**   | Simple grayscale digits (28x28) |
| CIFAR-10  | 5000  | 68.25%       | Complex RGB images (32x32)      |

🧾 **Performance Gap Analysis**
- CIFAR-10 is more complex (colors, textures, objects)
- Basic CNN is sufficient for MNIST but underpowered for CIFAR-10
- Need deeper models and better regularization for complex datasets

---

### 🔹 Part VI: Improving CNN Performance (CIFAR-10)

📐 **Updated Architecture**:
- Added **Conv3**: 128 filters → MaxPool(2x2)
- New flattened shape: 4x4x128 → 2048 units
- Dense(1024) → Dense(10)

📊 **Result**:
- New Peak Accuracy: **69.38%**
- Improvement over previous model (68.25%)

> Although small, this increase confirms the benefit of deeper CNNs for complex image recognition.

---

## 🚀 Summary of Learnings

- **Simple CNNs** perform well on MNIST due to simplicity of the data
- **Deeper CNNs** are needed for CIFAR-10 due to higher data complexity
- Improvements through:
  - Additional convolution layers
  - Dropout for regularization
  - Potential for further gains via data augmentation, batch normalization, longer training

---

## 🛠️ Technologies & Tools
- Python
- TensorFlow / PyTorch (assumed)
- NumPy, Matplotlib
- CIFAR-10 & MNIST datasets

---

## ✅ Future Recommendations
- Apply **data augmentation** for CIFAR-10
- Implement **batch normalization** and **weight decay**
- Test **learning rate schedules**
- Increase training steps beyond 5000

---

📌 This project showcases the importance of **model complexity matching data complexity**. CNNs can perform exceptionally well when thoughtfully designed and tuned for the dataset.

