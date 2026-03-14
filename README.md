# 🧠 VisionNet | Image Classification using CNN on CIFAR-10

![Python](https://img.shields.io/badge/Python-3.13-blue?style=for-the-badge&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red?style=for-the-badge&logo=pytorch)
![Accuracy](https://img.shields.io/badge/Test%20Accuracy-74.71%25-brightgreen?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

---

## 📌 Problem Statement

Image classification is a fundamental problem in Computer Vision where a model must correctly identify what object is present in an image. Manual classification of large-scale image datasets is time-consuming and error-prone.

This project builds a **Convolutional Neural Network (CNN) from scratch** to automatically classify images into 10 distinct categories using the **CIFAR-10 dataset** — a standard benchmark dataset in deep learning.

---

## 📂 Dataset

| Property | Details |
|---|---|
| Dataset | CIFAR-10 |
| Total Images | 60,000 (32×32 color images) |
| Training Set | 50,000 images |
| Test Set | 10,000 images |
| Classes | 10 (Airplane, Automobile, Bird, Cat, Deer, Dog, Frog, Horse, Ship, Truck) |

---

## 🏗️ Model Architecture

```
Input (3 × 32 × 32)
        ↓
Conv2D(32 filters) → ReLU → MaxPool(2×2)
        ↓
Conv2D(64 filters) → ReLU → MaxPool(2×2)
        ↓
Conv2D(128 filters) → ReLU → MaxPool(2×2)
        ↓
Flatten → FC(256) → ReLU → FC(10)
        ↓
Output (10 classes)
```

- **3 Convolutional Blocks** with progressively increasing filters (32 → 64 → 128)
- **ReLU Activation** after each convolutional layer
- **MaxPooling** for spatial dimensionality reduction
- **Fully Connected Layers** — 256 hidden units → 10 output classes
- **Loss Function** — CrossEntropyLoss
- **Optimizer** — Adam

---

## 🚀 How I Solved It

1. **Data Preprocessing** — Applied normalization `(mean=0.5, std=0.5)` across all 3 RGB channels and converted images to tensors using `torchvision.transforms`
2. **DataLoaders** — Used `batch_size=64` with shuffling for training to improve generalization
3. **Model Design** — Built a custom CNN class in PyTorch using `nn.Module` with sequential convolutional and fully connected layers
4. **Training Loop** — Ran 10 epochs, computing forward pass → loss → backpropagation → weight update using Adam optimizer
5. **Evaluation** — Evaluated the model in `torch.no_grad()` mode on the test set to compute final accuracy

---

## 📊 Training Results

| Epoch | Training Loss |
|---|---|
| 1 | 0.7556 |
| 2 | 0.6322 |
| 3 | 0.5293 |
| 4 | 0.4282 |
| 5 | 0.3469 |
| 6 | 0.2791 |
| 7 | 0.2118 |
| 8 | 0.1725 |
| 9 | 0.1350 |
| 10 | 0.1135 |

> ✅ **Final Test Accuracy: 74.71%**

---

## ⚠️ Challenges Faced

- **Overfitting Risk** — Training loss dropped significantly but test accuracy plateaued, indicating potential overfitting without dropout/batch normalization
- **Hyperparameter Tuning** — Selecting optimal batch size, learning rate, and number of filters required experimentation
- **Computational Load** — Training CNNs on CPU is slow; batch processing and efficient DataLoaders were critical for manageable training time
- **Architecture Design** — Deciding the depth of the network and filter sizes to balance accuracy vs. complexity

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.13 | Core programming language |
| PyTorch | Deep learning framework |
| Torchvision | Dataset loading & transforms |
| CIFAR-10 | Benchmark image dataset |
| Jupyter Notebook | Development environment |
| Adam Optimizer | Model optimization |
| CrossEntropyLoss | Multi-class loss function |

---

## 📁 Project Structure

```
VisionNet-CNN-CIFAR10/
│
├── CNN_for_CIFAR10.ipynb   # Main notebook with full implementation
├── README.md               # Project documentation
└── data/                   # CIFAR-10 dataset (auto-downloaded)
```

---

## ▶️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/abbas2407/VisionNet-CNN-CIFAR10.git
cd VisionNet-CNN-CIFAR10

# 2. Install dependencies
pip install torch torchvision jupyter

# 3. Launch Jupyter Notebook
jupyter notebook CNN_for_CIFAR10.ipynb
```

> The CIFAR-10 dataset will be **automatically downloaded** on first run.

---

## 🔮 Future Improvements

- Add **Dropout** and **Batch Normalization** to reduce overfitting
- Experiment with **deeper architectures** (ResNet-style blocks)
- Apply **Data Augmentation** (random flips, crops) to improve generalization
- Train on **GPU (CUDA)** for faster experimentation
- Target **85%+** accuracy with tuned hyperparameters

---

## 👤 Author

**Abbas Ali Palsaniya**
📧 abbas.off24@gmail.com
💼 [LinkedIn](https://www.linkedin.com/in/abbasalip)
💻 [GitHub](https://github.com/abbas2407)

---

*⭐ If you found this project helpful, consider giving it a star!*
