# Road Extraction Using U-Net

## Project Overview
This project implements a deep learning pipeline for automatic road extraction from satellite imagery using a U-Net convolutional neural network architecture. The goal is to accurately and efficiently segment road networks from high-resolution aerial and satellite images, supporting applications in urban planning, navigation systems, and disaster response.

## Dataset
- **DeepGlobe Road Extraction Dataset**
- High-resolution satellite images paired with annotated binary road masks
- Dataset split into training, validation, and testing subsets to ensure fair evaluation

## Preprocessing
- Images and masks converted into standardized input format
- Resizing to 256×256 pixels
- Normalization of pixel values
- Data augmentation applied to improve robustness:
  - Random rotation
  - Horizontal and vertical flipping
  - Random zoom

## Model Architecture
- **Base Model:** U-Net
- Key layers:
  - Convolutional + ReLU activation
  - Max-pooling for downsampling
  - Dropout for regularization
  - Transposed convolution for upsampling
- Output activation: Sigmoid
- Optimizer: Adam (learning rate = 1e-4)
- Loss function: Binary Cross-Entropy + Dice Loss

## Training Procedure
- Epochs: 10
- Batch size: 4
- Evaluation metrics:
  - Accuracy
  - Dice Coefficient
  - Intersection over Union (IoU)
- Early stopping and checkpointing enabled to avoid overfitting

## Metrics and Results
Final results demonstrate competitive performance on the validation set.

| Metric              | Value   |
|---------------------|---------|
| Accuracy            | ~97.2%  |
| Dice Coefficient    | ~0.66   |
| Intersection over Union (IoU) | ~0.53 |

### Training Curves
![Training Curves](training_curves.png)

### Example Segmentation Results
![Segmentation Results](fig_results.png)

## Features
- Preprocessing pipeline for preparing satellite images and masks  
- U-Net implementation tailored for binary segmentation of roads  
- Automatic checkpointing and early stopping  
- Exported metrics in multiple formats (CSV, JSON)  
- Visualizations comparing predictions against ground truth for qualitative evaluation  

## Future Work
Potential directions to extend this project include:  
- Expanding the dataset with diverse satellite imagery  
- Implementing attention-based U-Net variants to better capture thin road structures  
- Deploying the trained model in real-time applications (e.g., web-based demo with Streamlit)  
- Exploring semi-supervised learning to reduce dependence on labeled data  

## Contribution
Contributions are welcome to enhance the robustness and usability of this project. Potential contributions may include refining preprocessing techniques, experimenting with novel architectures (e.g., attention-based U-Net variants), or extending the dataset.  

The standard GitHub workflow applies for contributions:
1. Fork the repository  
2. Create a new branch for your feature or fix  
3. Commit your changes with clear descriptions  
4. Open a Pull Request for review  

This structure ensures collaborative, high-quality improvements to the project.

## Conclusion
This project demonstrates the application of U-Net for road extraction from satellite images. The model achieved strong results with high accuracy, competitive Dice and IoU scores, and visual confirmation of effective road segmentation.  

All outputs—including metrics, training curves, and segmentation examples—are provided in this repository. The work serves as a baseline for further research in geospatial deep learning and potential applications in transportation planning, navigation, and disaster management.  


**Kaggle Notebook Link:** [(https://www.kaggle.com/code/nurbali/road-extraction-unet-cnn)]  
**GitHub Repository Link:** [(https://github.com/nurbalicc-cmd/road-extraction-unet/edit/main/README.md)]  
