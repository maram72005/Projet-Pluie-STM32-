# 🌧️ Rain Prediction AI for STM32 

This project uses a **Deep Learning** model to predict if it is raining based on **Temperature** and **Humidity** sensors. The model is designed to be lightweight and compatible with **STM32 microcontrollers** (Cortex-M).



## 📌 Project Overview
The goal is to train a small Neural Network in Python (TensorFlow/Keras) and deploy it on an embedded system. 

* **Inputs:** Temperature (°C), Humidity (%)
* **Output:** Binary Classification (1: Raining, 0: Dry)
* **Target Hardware:** STM32F series (optimized for low memory).

## 📊 Dataset
The model is trained using an Excel dataset (`METEO.xlsx`) containing historical weather records. 
* **Preprocessing:** We use `pandas` to clean data and `scikit-learn` to split the data (80% Train / 20% Test).
* **Data Type:** All values are converted to `float32` for STM32 compatibility.



## 🧠 Model Architecture
The Neural Network is a simple **Multilayer Perceptron (MLP)**:
1.  **Input Layer:** 16 neurons (ReLU activation)
2.  **Hidden Layer:** 8 neurons (ReLU activation)
3.  **Output Layer:** 1 neuron (Sigmoid activation)

This small architecture ensures low latency and minimal RAM usage on the microcontroller.


This project uses a simple **Neural Network** to predict if it is raining based on **Temperature** and **Humidity**. It is designed to be very small and fast to run on an **STM32 microcontroller**.

## ⚙️ How it Works (Simple Steps)
1.  **Data Cleaning:** We use `pandas` to remove empty lines and prepare the numbers.
2.  **Training:** The AI studies the data 50 times (**50 Epochs**) to find patterns.
3.  **Testing:** we use 20% of the data to give the AI a "Final Exam" (The **Golden Rule**).
4.  **Conversion:** We transform the model into a **TFLite** file so the STM32 can read it.

## 📊 Results
* **Accuracy:** ~85-90% (The AI's final grade).
* **Model Size:** Very small (Low memory usage for **Cortex-M**).



## 🛠️ Next Step
The next part of this project is to import `modele_pluie.tflite` into **STM32CubeIDE** using the **X-CUBE-AI** plugin to turn the AI into C code.
