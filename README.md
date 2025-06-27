# CIFAR-10 Classification Benchmark Study

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1mqJNx2Hq5ZPrrwBeJxHe7Bu4otjkR4wJ?usp=sharing)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?logo=pytorch)](https://pytorch.org)
<!--
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?logo=tensorflow)](https://tensorflow.org)
-->


> **Brief Description:** This project implements and benchmarks several deep learning models for classifying the CIFAR-10 dataset. The goal is to compare the performance of different architectures, ranging from a custom Convolutional Neural Network (CNN) to pre-trained models like ResNet and Inception, as well as a custom network with advanced features like residual connections and depthwise separable convolutions.

<!--
## 📋 Table of Contents

- [🎯 Overview](#-overview)
- [✨ Features](#-features)
- [🔧 Installation](#-installation)
- [🚀 Quick Start](#-quick-start)
- [📊 Dataset](#-dataset)
- [🏗️ Model Architecture](#️-model-architecture)
- [📈 Results](#-results)
- [🛠️ Usage](#️-usage)
- [📝 Documentation](#-documentation)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [🙏 Acknowledgments](#-acknowledgments)

## 🎯 Overview

Provide a comprehensive overview of your project here. Explain:
- What problem you're solving
- Why this project matters
- Your approach to solving it
- Key innovations or contributions

### 🔬 Research Context

- **Domain**: Computer Vision / NLP / Time Series / etc.
- **Task**: Classification / Regression / Generation / etc.
- **Methodology**: Deep Learning / Traditional ML / Hybrid Approach

## ✨ Features

- 🎯 **Feature 1**: Description of key feature
- 📊 **Feature 2**: Another important capability
- ⚡ **Feature 3**: Performance or efficiency highlight
- 🔍 **Feature 4**: Analysis or visualization feature
- 📱 **Interactive**: Easy-to-use Colab interface

## 🔧 Installation

### Prerequisites

```bash
# Required Python packages (automatically installed in Colab)
tensorflow>=2.10.0
torch>=1.12.0
numpy>=1.21.0
pandas>=1.3.0
matplotlib>=3.5.0
seaborn>=0.11.0
scikit-learn>=1.1.0
```

### Setup in Google Colab

1. **Open the notebook**: Click the "Open in Colab" badge above
2. **Runtime setup**: Go to `Runtime` → `Change runtime type` → Select `GPU`
3. **Install dependencies**: Run the first cell to install required packages
4. **Mount Google Drive** (if needed): For accessing custom datasets

```python
# Mount Google Drive (optional)
from google.colab import drive
drive.mount('/content/drive')
```

## 🚀 Quick Start

### Option 1: Google Colab (Recommended)

1. Click the **"Open in Colab"** badge above
2. Run all cells in sequence
3. Modify parameters in the configuration section as needed

### Option 2: Local Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name

# Install dependencies
pip install -r requirements.txt

# Run Jupyter notebook
jupyter notebook notebook.ipynb
```
-->

## 📊 Dataset

### Dataset Information

- **Name**: CIFAR-10
- **Source**: Downloaded in Colab using _"torchvision.datasets.CIFAR10(root='./data', download=True)"_
- **Size**:  It consists of 60,000 32x32 colour images in 10 classes, with 6,000 images per class. There are 50,000 training images and 10,000 test images.
- **Format**: Images
<!--
- **License**: [Dataset license]
-->

<!--
### Data Structure

```
dataset/
├── train/
│   ├── class_1/
│   └── class_2/
├── validation/
└── test/
```

### Data Preprocessing

- **Normalization**: Min-Max scaling applied
- **Augmentation**: Random rotation, flip, zoom
- **Split**: 70% train, 15% validation, 15% test
-->

## 🧠 Model Architecture

### Model Overview

The following models are implemented and evaluated in this study:

- **Custom CNN Classifier:** A standard convolutional neural network architecture designed specifically for the CIFAR-10 dataset.
- **AlexNet Classifier:** An implementation of the classic AlexNet architecture, adapted for CIFAR-10.
- **Pre-trained ResNet Model:** Fine-tuning of a pre-trained ResNet model (ResNet18) on the CIFAR-10 dataset.
- **Pre-trained Inception Model:** Fine-tuning of a pre-trained Inception V3 model on the CIFAR-10 dataset.
- **Custom Network Architecture:** A novel architecture incorporating residual connections and depthwise separable convolutions for improved performance and efficiency.

The project extensively uses the following Python libraries:

- **PyTorch:** The primary deep learning framework used for building, training, and evaluating the models.
- **torchvision:** Provides access to standard datasets, model architectures, and image transformations.
- **matplotlib:** Used for visualizing model training progress and performance comparisons.
- **numpy:** Used for numerical operations.
- **time:** Used for measuring training time.

<!--
### Architecture Diagram

```
Input → [Preprocessing] → [Feature Extraction] → [Classification] → Output
```

### Hyperparameters

| Parameter | Value | Description |
|-----------|--------|-------------|
| Learning Rate | 0.001 | Initial learning rate |
| Batch Size | 32 | Training batch size |
| Epochs | 100 | Maximum training epochs |
| Optimizer | Adam | Optimization algorithm |
| Loss Function | CrossEntropy | Loss function used |
-->

## 📈 Results

<table>

<tr>
<td colspan="2" align="center">

#### MODEL PERFORMANCE COMPARISON

</td>
</tr>

<tr>
<td>

| Model                | Accuracy (%) |
| ---------------------|--------------|
| CNN                  |        86.23 |
| AlexNet              |        82.91 |
| ResNet               |        61.70 |
| Inception            |        74.89 |
| Custom Architecture  |        67.59 |

</td>
<td>

![Performance Comparison](https://raw.githubusercontent.com/ritanjit/CIFAR-10_Classification_Models/main/Model_Comparision.png) 

</td>
</tr>
</table>


<!--
### Training Curves

*Include training/validation loss and accuracy plots here*

### Confusion Matrix

*Include confusion matrix visualization*

### Key Findings

- 📊 **Finding 1**: Significant improvement over baseline
- 🎯 **Finding 2**: Model performs well on edge cases
- ⚡ **Finding 3**: Efficient inference time

## 🛠️ Usage

### Basic Usage

```python
# Load the trained model
model = load_model('path/to/model')

# Make predictions
predictions = model.predict(input_data)

# Process results
results = process_predictions(predictions)
```

### Advanced Usage

```python
# Custom training loop
for epoch in range(num_epochs):
    train_loss = train_step(model, train_data)
    val_loss = validate_step(model, val_data)
    
    # Log metrics
    log_metrics(epoch, train_loss, val_loss)
```
-->

## ⚙️ Configuration

### How to Run the Code

1.  Open the Colab notebook file (`.ipynb`).
2.  Ensure you have access to a GPU runtime for faster training (Runtime -> Change runtime type).
3.  Run all cells in the notebook sequentially. The notebook will download the dataset, define the models, train them, and evaluate their performance.

### Files

*   `.ipynb`: The main Colab notebook containing all the code.
*   `model_comparison.png`: A bar chart visualizing the performance comparison.

## 🚀 Future Work

*   Experiment with different hyperparameters for each model.
*   Implement additional model architectures (e.g., DenseNet, VGG).
*   Explore data augmentation techniques to further improve performance.
*   Analyze misclassifications in more detail to understand model weaknesses.

<!--
## 📝 Documentation

### Notebook Sections

1. **Setup & Imports**: Required libraries and configurations
2. **Data Loading**: Dataset preparation and exploration
3. **Preprocessing**: Data cleaning and augmentation
4. **Model Definition**: Architecture and compilation
5. **Training**: Model training with monitoring
6. **Evaluation**: Performance assessment
7. **Visualization**: Results and analysis plots
8. **Export**: Model saving and deployment prep

### API Reference

*Link to detailed API documentation if available*

### Troubleshooting

**Common Issues:**

- **GPU Memory Error**: Reduce batch size in config
- **Package Conflicts**: Restart runtime and reinstall
- **Data Loading Issues**: Check file paths and permissions

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md).

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
pytest tests/

# Format code
black .
isort .
```


## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Dataset**: Thanks to [Dataset Provider] for providing the dataset
- **Base Model**: Built upon [Model/Framework Name]
- **Inspiration**: Inspired by [Paper/Project Name]
- **Community**: Special thanks to the [Community Name] community

### Citations

If you use this project in your research, please cite:

```bibtex
@misc{your_project_2024,
  title={Your Project Title},
  author={Your Name},
  year={2024},
  url={https://github.com/yourusername/your-repo-name}
}
```
### References

1. [Paper Title](paper-url) - Original research paper
2. [Framework Documentation](framework-url) - Technical documentation
3. [Dataset Paper](dataset-paper-url) - Dataset description
-->
---

<div align="center">

**⭐ Star this repo if you found it helpful!**
<!--
[Report Bug](https://github.com/yourusername/your-repo-name/issues) · [Request Feature](https://github.com/yourusername/your-repo-name/issues) · [Documentation](https://github.com/yourusername/your-repo-name/wiki)
-->

Made with ❤️ by [Ritanjit](https://github.com/ritanjit)

</div>
