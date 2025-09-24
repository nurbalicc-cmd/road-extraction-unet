# Road Extraction with U-Net (AI Bootcamp 2025)

## Introduction
This project focuses on **road extraction from satellite imagery** using a **U-Net convolutional neural network (CNN)**. The primary goal is to automate the segmentation of roads from aerial images, which is a crucial step for applications in **autonomous navigation, urban planning, and disaster management**.  

This repository is part of the **Global AI Hub & Akbank AI Bootcamp 2025** program.  

---

## Dataset
- **Source:** [DeepGlobe Road Extraction Dataset](https://competitions.codalab.org/competitions/18467)  
- **Content:** High-resolution satellite images and corresponding binary road masks.  
- **Split:**  
  - Training: 4,980 images  
  - Validation: 1,246 images  
- Preprocessing included resizing images to 256×256 pixels and normalizing pixel values.  

---

## Methodology
- **Model:** U-Net (lightweight version for faster training).  
- **Framework:** TensorFlow / Keras.  
- **Training setup:**  
  - Optimizer: Adam  
  - Loss: Binary Cross-Entropy + Dice loss  
  - Metrics: Accuracy, Dice Coefficient, IoU  

---

## Results

### Metrics
| Metric      | Train | Validation |
|-------------|-------|------------|
| Accuracy    | 0.97+ | ~0.97      |
| Dice Coef.  | ~0.67 | ~0.66      |
| IoU Metric  | ~0.50 | ~0.49      |
| Loss        | ~0.39 | ~0.43      |

---

### Training Curves
![Training Curves](training_curves.png)

---

### Example Predictions
Below are examples comparing input images, ground-truth masks, and model predictions:

![Example Results](fig_results.png)

---

## Discussion
- The U-Net model successfully learned to extract road networks from satellite imagery.  
- Performance is consistent across training and validation, showing limited overfitting.  
- Small roads and intersections remain challenging, reflecting the need for either more data augmentation or deeper architectures.  

---

## Future Work
- Integrating **attention-based U-Net** or **transformer-based architectures** to improve fine-grained road detection.  
- Experimenting with **data augmentation techniques** for robustness.  
- Deploying the trained model in a **web-based tool (Streamlit)** for real-time road segmentation.  

---

## Reproducibility
You can reproduce the results by running the Kaggle notebook:  
[Road Extraction U-Net CNN – Kaggle Notebook (v6)](https://www.kaggle.com/code/nurbali/road-extraction-unet-cnn)

---
## References
- DeepGlobe 2018 Road Extraction Challenge: [https://competitions.codalab.org/competitions/18467](https://competitions.codalab.org/competitions/18467)  
- Ronneberger, O., Fischer, P., & Brox, T. (2015). **U-Net: Convolutional Networks for Biomedical Image Segmentation.** arXiv:1505.04597  
- Bootcamp-provided project guidelines and resources (Global AI Hub, 2025).  
