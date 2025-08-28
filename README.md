# Deep Learning Assignments – Hochschule Heilbronn

This repository documents my **Deep Learning assignments** at **Hochschule Heilbronn**.  
The assignments cover fundamental deep learning concepts and their applications in computer vision and time-series forecasting.  

---

##  Assignment 1: MNIST Handwritten Digit Recognition

### Model Architecture
- **Type:** `Sequential` (Keras)  
- **Hidden Layers:**  
  - Dense layers with **ReLU activation**  
    - ReLU avoids the **vanishing gradient problem**  
  - Dropout layers to reduce overfitting and encourage more generalizable features  
- **Output Layer:** `Softmax` activation for multi-class classification  

### Loss Function
- **`sparse_categorical_crossentropy`**  
  - Appropriate because MNIST labels are integers (0–9)  
  - Classes are **mutually exclusive**, so we don’t need probability overlap  

### Optimizer
- **`Adam`**  
  - Adapts learning rate dynamically  
  - Works well for large image datasets in computer vision  
  - Converges faster than vanilla SGD  

---

##  Assignment 2: Neural Style Transfer

### Overview
The goal of this assignment is to implement **Neural Style Transfer (NST)** using a **pre-trained VGG16** model.  
NST generates new images by combining:
- **Content image:** Defines the subject of the output image  
- **Style image:** Provides artistic textures and colors  
- **Generated image:** Optimized to balance style and content  

### Requirements
- Python 3.x  
- TensorFlow  
- NumPy  

### Model Architecture
- **Pre-trained Model:** `VGG16` (trained on ImageNet)  
- **Feature Extraction:**  
  - Lower layers capture textures and styles  
  - Higher layers capture semantic content  
- **Optimization Objective:**  
  - **Content Loss** – ensures generated image preserves subject structure  
  - **Style Loss** – ensures textures/colors of style image are transferred  
  - **Total Variation Loss** – encourages spatial smoothness  

### Training Strategy
- Use **Adam optimizer**  for convergence  

---

##  Assignment 3: Stock Price Prediction with LSTM

### Overview
This assignment applies **Long Short-Term Memory (LSTM)** networks to predict stock price movements.  
We use **closing prices** as the primary feature for forecasting.

### Requirements
- Python 3.x  
- TensorFlow / Keras  
- NumPy  
- Pandas  
- Matplotlib

### Data Preprocessing
- Extract **closing prices** from stock market data  
- Drop missing values  
- Transform prices into **log returns** to better capture relative changes  

### Model Architecture
- **LSTM Layers:** Capture sequential dependencies in time-series data  
- **Dense Output Layer:** Provides stock return predictions  
- **Loss Function:** `Mean Squared Error (MSE)` – suitable for regression tasks  
- **Optimizer:** `Adam` – adapts learning rate dynamically and converges quickly   