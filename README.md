# 🥔 PotatoClassification

A deep learning application that uses Convolutional Neural Networks (CNNs) to classify potato plant leaves as **Blight** or **Non-Blight**, helping farmers in India detect fungal infections early and protect their crops.

---

## 🌿 About the Project

Late blight and early blight are fungal diseases that devastate potato crops, caused by *Phytophthora infestans* and *Alternaria solani* respectively. Left undetected, these diseases can destroy entire harvests.

This project trains a CNN model on images of potato leaves to automatically detect whether a crop is infected — giving farmers a fast, accessible tool for early intervention without requiring expert agronomists on-site.

---

## 🧠 How It Works

1. **Image Input** — A photo of a potato plant leaf is captured (via camera or upload).
2. **Preprocessing** — The image is resized, normalized, and prepared for the model.
3. **CNN Inference** — A trained Convolutional Neural Network classifies the leaf.
4. **Output** — The app reports whether the crop is **Blighted** or **Healthy (Non-Blight)**.

---

## 📁 Project Structure

```
PotatoClassification/
│
├── data/                   # Dataset: blight and non-blight leaf images
│   ├── train/
│   │   ├── blight/
│   │   └── non_blight/
│   └── val/
│       ├── blight/
│       └── non_blight/
│
├── models/                 # Saved trained model weights
│
├── notebooks/              # Jupyter notebooks for training and EDA
│
├── src/
│   ├── train.py            # Model training script
│   ├── predict.py          # Run inference on new images
│   └── preprocess.py       # Image preprocessing utilities
│
├── app/                    # Web/mobile interface (if applicable)
│
├── requirements.txt
└── README.md
```

> **Note:** This structure will evolve as the project is built out.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- pip
- (Recommended) A GPU with CUDA support for faster training

### Installation

```bash
git clone https://github.com/sleepypant/PotatoClassification.git
cd PotatoClassification
pip install -r requirements.txt
```

### Dataset

This project uses the [PlantVillage dataset](https://www.kaggle.com/datasets/emmarex/plantdisease) available on Kaggle, which includes labeled images of potato leaves across three categories:

- Potato — Early Blight
- Potato — Late Blight
- Potato — Healthy

Download the dataset and place the relevant folders inside the `data/` directory.

### Training the Model

```bash
python src/train.py --epochs 25 --batch_size 32
```

### Running a Prediction

```bash
python src/predict.py --image path/to/leaf_image.jpg
```

---

## 🏗️ Model Architecture

The classifier is built using a CNN architecture. The current approach:

- **Base model:** Custom CNN (with plans to benchmark against transfer learning approaches such as ResNet50 or EfficientNet)
- **Input:** RGB images, resized to 256×256
- **Output:** Binary classification — Blight / Non-Blight
- **Loss:** Binary Cross-Entropy
- **Optimizer:** Adam

---

## 📊 Results

| Metric    | Value |
|-----------|-------|
| Accuracy  | TBD   |
| Precision | TBD   |
| Recall    | TBD   |
| F1 Score  | TBD   |

> Results will be updated as training experiments are completed.

---

## 🌾 Real-World Use Case

This tool is designed for farmers in India who need a practical, low-cost way to monitor their crops. The goal is to deploy this as a simple mobile-friendly web app where a farmer can take a photo of a leaf and receive an immediate diagnosis — no internet required (offline inference planned).

---

## 🗺️ Roadmap

- [x] Repository setup
- [ ] Data collection and preprocessing pipeline
- [ ] Baseline CNN model training
- [ ] Transfer learning experimentation
- [ ] Model evaluation and tuning
- [ ] Simple web/mobile UI for farmers
- [ ] Offline inference support
- [ ] Hindi language support in UI

---

## 🤝 Contributing

Contributions are welcome! Please open an issue first to discuss any major changes. Pull requests for bug fixes, dataset improvements, or model enhancements are encouraged.

---

## 📄 License

This project is licensed under the [Apache 2.0 License](LICENSE).

---

## 🙏 Acknowledgements

- [PlantVillage Dataset](https://www.kaggle.com/datasets/emmarex/plantdisease) — for the labeled leaf images
- [TensorFlow](https://www.tensorflow.org/) / [PyTorch](https://pytorch.org/) — deep learning frameworks
- Farmers across India whose livelihoods inspired this project
