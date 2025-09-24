# Road Extraction Using U-Net

## Project Overview
This project implements a deep learning pipeline for automatic road extraction from satellite imagery using a U-Net convolutional neural network architecture. The objective is to segment road networks accurately and efficiently from high-resolution aerial and satellite images. Such models have important applications in transportation planning, navigation systems, and disaster response scenarios.

---

## Dataset
- **DeepGlobe Road Extraction Dataset (2018 Challenge)**  
- High-resolution RGB satellite images paired with binary road masks  
- Data split: **training (80%)**, **validation (10%)**, and **testing (10%)**  
- Masks encoded with **1 = road** and **0 = background**

---

## Preprocessing
A standardized preprocessing pipeline was applied to ensure consistency and improve model robustness:
- Image resizing to **256×256 pixels**
- Pixel value normalization to [0, 1] range
- Data augmentation techniques:  
  - Random rotations  
  - Horizontal and vertical flips  
  - Random zoom  

---

## Model Architecture
The project uses a **U-Net** encoder–decoder CNN with skip connections.

**Key Design Choices**
- Convolutional blocks with ReLU activation
- Max pooling for downsampling
- Dropout layers for regularization
- Sigmoid activation for binary mask prediction
- Optimizer: **Adam** with learning rate = 1e-4
- Loss function: **Binary Cross-Entropy + Dice Loss**

---

## Training Procedure
- **Epochs:** 10  
- **Batch size:** 4  
- **Metrics monitored:** Accuracy, Dice Coefficient, IoU  
- Early stopping and checkpointing to retain the best weights  

---

## Metrics and Results
The trained model achieved competitive performance across multiple metrics.  

| Metric              | Training | Validation |
|---------------------|----------|------------|
| Accuracy            | ~0.98    | ~0.972     |
| Dice Coefficient    | ~0.67    | ~0.66      |
| Intersection over Union (IoU) | ~0.50 | ~0.53 |
| Loss                | ~0.39    | ~0.42      |

**Training Curves:**  
![Training Curves](training_curves.png)

**Example Segmentation Results:**  
![Segmentation Results](fig_results.png)

Visual inspection confirms that the model successfully extracts major road structures, although very thin or occluded roads remain challenging.

---

## Saved Artifacts
The repository contains all key outputs for reproducibility:
- **Trained model:** `unet_ft_best.keras`
- **Final weights:** `unet_final.weights.h5`
- **Metrics:** `metrics.json`, `metrics_table.csv`, `val_metrics.json`
- **Figures:** `training_curves.png`, `fig_results.png`

---

## Features
- End-to-end preprocessing pipeline for satellite data  
- U-Net implementation tailored to binary segmentation tasks  
- Checkpointing and early stopping integrated  
- Metrics exported in both JSON and CSV formats  
- Qualitative evaluation through prediction visualizations  

---

## Future Work
Potential directions for extending this project include:
- Expanding training with larger and more diverse datasets  
- Exploring **attention-based U-Net variants** to better capture thin roads  
- Deploying the model via a web-based app (e.g., Streamlit)  
- Experimenting with semi-supervised or weakly-supervised learning approaches  

---

## Contribution
Contributions are welcome to improve this project further.  

**Steps to contribute:**
1. Fork the repository  
2. Create a feature branch  
3. Commit and document your changes clearly  
4. Open a Pull Request for review  

---

## Conclusion
This project demonstrates the feasibility of applying U-Net architectures to extract road networks from satellite imagery. The model reached strong Dice and IoU scores, supported by visual confirmation of accurate segmentation results. While thin and noisy roads remain a challenge, the pipeline provides a reliable baseline for further research in geospatial deep learning.  

The project highlights potential applications in real-world domains such as **urban planning, navigation systems, and emergency response**. It also serves as a foundation for future enhancements including larger datasets, attention mechanisms, and deployment in production environments.  

**Kaggle Notebook Link:** [Insert public Kaggle notebook link here]  
**GitHub Repository Link:** [Insert GitHub repository link here]  
