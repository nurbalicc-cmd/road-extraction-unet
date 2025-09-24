# Road Extraction U-Net

Deep learning project for road extraction from satellite imagery using a U-Net architecture. The project was developed as part of the AI Bootcamp 2025.

---

## Table of Contents
- [Dataset](#dataset)  
- [Model Architecture](#model-architecture)  
- [Usage](#usage)  
- [Metrics and Results](#metrics-and-results)  
- [Features](#features)  
- [Future Work](#future-work)  
- [Contribution](#contribution)  
- [Conclusion](#conclusion)  

---

## Dataset
The dataset consists of satellite images paired with binary road masks. Images were preprocessed to ensure consistent dimensions and scaling. Masks represent road pixels with value 1 and background pixels with value 0.  

---

## Model Architecture
The project implements a U-Net architecture tailored for binary segmentation tasks. Key design choices:  
- Convolutional encoder-decoder structure with skip connections.  
- Input: 256×256 RGB satellite images.  
- Output: 256×256 binary masks indicating road locations.  
- Loss function: Binary Cross-Entropy + Dice loss.  
- Optimizer: Adam with learning rate scheduling.  

---

## Usage
1. Clone the repository and install dependencies:
   ```bash
   git clone https://github.com/your-username/road-extraction-unet.git
   cd road-extraction-unet
   pip install -r requirements.txt
Run the notebook step by step to:

Preprocess the dataset

Train the U-Net model

Evaluate metrics

Generate predictions and plots

Outputs include:

Training curves (training_curves.png)

Example segmentation results (fig_results.png)

Metrics (metrics.json, metrics_table.csv)

Best model weights

Metrics and Results

The trained model achieved competitive performance:

Accuracy: ~0.98

Dice Coefficient: ~0.67

IoU: ~0.50

Loss: ~0.39

Training and validation curves demonstrate convergence and stability. Visual inspection of predictions confirms that the model effectively extracts road structures from diverse satellite images.

Features

Preprocessing pipeline for preparing satellite images and masks.

U-Net implementation tailored for binary segmentation of roads.

Automatic checkpointing and early stopping.

Exported metrics in multiple formats (CSV, JSON).

Visualizations of predictions versus ground truth for qualitative evaluation.

Future Work

Potential directions to extend this project include:

Expanding the dataset with diverse satellite imagery.

Implementing attention-based U-Net variants to enhance segmentation of thin road structures.

Deploying the trained model in real-time applications (e.g., web-based demo with Streamlit).

Exploring semi-supervised learning to reduce dependence on labeled datasets.

Contribution

Contributions are encouraged to improve the project further.

Steps to contribute:

Fork the repository.

Create a new branch for your feature or fix.

Commit and describe your changes clearly.

Open a Pull Request for review.

Conclusion

This project demonstrates the application of U-Net for road extraction from satellite images. The model achieved competitive results with strong Dice and IoU scores, supported by visual confirmation of accurate road segmentation. All outputs—including metrics, curves, and predictions—are provided in the repository.

The project serves as a baseline for further research in geospatial deep learning and potential real-world applications in transportation planning, navigation systems, and disaster response.

Kaggle Notebook Link: [Insert your public Kaggle notebook link here]
GitHub Repository Link: [Insert your GitHub repository link here]
