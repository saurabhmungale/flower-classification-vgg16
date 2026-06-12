# 🌸 Flower Classification using VGG16 Transfer Learning

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![Keras](https://img.shields.io/badge/Keras-Transfer%20Learning-red.svg)
![Accuracy](https://img.shields.io/badge/Accuracy-81%25-brightgreen.svg)

A deep learning project that classifies **5 types of flowers** using **VGG16 Transfer Learning** with TensorFlow and Keras. The model is trained on ~3,670 flower images and achieves **~81% test accuracy**.

---

## 🌼 Flower Classes

| Class | Label |
|-------|-------|
| 🌼 Daisy | 0 |
| 🌻 Sunflower | 1 |
| 🌷 Tulip | 2 |
| 🌱 Dandelion | 3 |
| 🌹 Rose | 4 |

---

## 📁 Project Structure

```
flower-classification-vgg16/
│
├── notebooks/
│   └── flower_classification_vgg16.ipynb   ← Main Colab Notebook
│
├── requirements.txt                         ← Python dependencies
├── .gitignore                               ← Files to exclude from Git
└── README.md                                ← Project documentation
```

---

## 🏗️ Model Architecture

```
Input (150x150x3)
        ↓
VGG16 Base Model (pretrained on ImageNet, layers FROZEN)
        ↓
GlobalAveragePooling (pooling='avg')
        ↓
Dense(256, activation='relu')
        ↓
Dense(5, activation='softmax')   ← 5 Flower Classes
```

- **Base Model** : VGG16 pretrained on ImageNet
- **Frozen Layers** : All VGG16 layers (Transfer Learning)
- **Custom Head** : Dense(256) + Dense(5, Softmax)
- **Optimizer** : Adam (lr = 1e-4)
- **Loss** : Categorical Crossentropy
- **Callback** : ReduceLROnPlateau

---

## 📊 Results

| Metric | Value |
|--------|-------|
| Test Accuracy | **~81%** |
| Epochs | 50 |
| Batch Size | 64 |
| Image Size | 150 × 150 |
| Train/Test Split | 80% / 20% |

---

## 🚀 How to Run

### ▶️ Run on Google Colab (Recommended)

1. Open the notebook in Google Colab
2. Set runtime to **GPU** for faster training:  
   `Runtime → Change runtime type → GPU`
3. Run all cells — the dataset downloads **automatically**
4. Training takes ~15–20 min on GPU

### 💻 Run Locally

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/flower-classification-vgg16.git
cd flower-classification-vgg16

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open the notebook
jupyter notebook notebooks/flower_classification_vgg16.ipynb
```

---

## 📦 Dataset

- **Source** : [TensorFlow Flower Photos](https://storage.googleapis.com/download.tensorflow.org/example_images/flower_photos.tgz)
- **Total Images** : ~3,670
- **Format** : JPEG
- **Auto-downloaded** via `tf.keras.utils.get_file()` — no manual setup needed

| Class | Images |
|-------|--------|
| Daisy | 633 |
| Sunflowers | 699 |
| Tulips | 799 |
| Dandelion | 898 |
| Roses | 641 |

---

## 🔧 Data Preprocessing & Augmentation

- Resized all images to **150 × 150**
- Converted BGR → RGB using OpenCV
- Normalized pixel values to **[0, 1]**
- Applied augmentation using `ImageDataGenerator`:
  - Rotation (±10°)
  - Zoom (10%)
  - Horizontal Flip
  - Width & Height Shift (20%)

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| TensorFlow / Keras | Model building & training |
| VGG16 | Pretrained base model |
| OpenCV | Image loading & preprocessing |
| NumPy | Array operations |
| Pandas | Data handling |
| Matplotlib / Seaborn | Visualization |
| Scikit-learn | Metrics & data splitting |
| tqdm | Progress bars |

---

## 📈 Training Details

- **Learning Rate Scheduler** : `ReduceLROnPlateau` reduces LR by 0.1x if `val_acc` doesn't improve for 2 epochs
- **Model saved** as `model.keras` after training
- **Confusion Matrix & Classification Report** generated for evaluation

---

## 🙋‍♂️ Author

**Saurabh**  
Data Science with Generative AI — PW Skills  
📍 Nagpur, Maharashtra, India  

[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?logo=github)](https://github.com/YOUR_USERNAME)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://linkedin.com/in/YOUR_PROFILE)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
