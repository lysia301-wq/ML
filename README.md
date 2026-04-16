
# Drowsiness Detection System

A deep learning–based computer vision project that detects driver fatigue by analyzing **eye states (Awake vs Sleepy)**. The goal is to build a lightweight, real-time ready model that can help prevent road accidents by triggering safety alerts.



##  Objectives

**Automated Detection**
Build a binary image classifier to distinguish between **Awake** and **Sleepy** eye states.

**Performance Optimization**
Compare a custom CNN with a **transfer learning model**.

**Efficiency**
Implement a **Speed Hack** to significantly reduce training time.

**Scalability**
Design a lightweight model suitable for **edge device deployment**.



##  Tech Stack

| Category        | Tools                    |
| --------------- | ------------------------ |
| Language        | Python                   |
| Deep Learning   | TensorFlow / Keras       |
| Data Processing | NumPy, Pandas, PIL       |
| Visualization   | Matplotlib, Scikit-learn |
| Environment     | Google Colab (GPU)       |



##  Key Features

✔ Real-time ready image size: **96 × 96**
✔ Data augmentation for robustness
✔ Ultra-fast training via local VM SSD transfer (**~100× faster**)
✔ Automatic saving of models and charts to **Google Drive**
✔ Lightweight model for future edge deployment

### Data Augmentation Includes

* Random rotation
* Horizontal flips
* Zoom augmentation



##  Models Implemented

###  Custom CNN Model (Baseline)

A CNN built from scratch to establish baseline performance.

**Architecture**

* 3 × Conv2D layers
* Batch Normalization
* MaxPooling
* Dropout (0.5)
* Dense Sigmoid classifier

**Result**

* Accuracy: **~74%**


###  MobileNetV2 (Transfer Learning)

A pre-trained model used as a feature extractor.

**Architecture**

* MobileNetV2 base (frozen)
* Global Average Pooling
* Dropout (0.2)
* Sigmoid output layer

**Result**

* Accuracy: **88.56%**
* Much higher recall and generalization



##  Evaluation Metrics (MobileNetV2)

| Metric               | Value      |
| -------------------- | ---------- |
| Accuracy             | **88.56%** |
| Precision            | 0.8678     |
| Recall (Sensitivity) | 0.9059     |
| F1-Score             | 0.8864     |
| Balanced Accuracy    | 0.8859     |

**Predictions Summary**

*  Correct Predictions: **1757**
*  Incorrect Predictions: **227**



##  How It Works

###  Data Acquisition

* Uses the **MRL Eye Dataset**
* Images categorized into:

  * Awake
  * Sleepy

###  Preprocessing

* Resize images → **96 × 96**
* Normalize pixel values

###  Feature Extraction

MobileNetV2 extracts:

* Edges
* Eye shape
* Eyelid position

###  Classification

Sigmoid output gives probability:

| Score | Result |
| ----- | ------ |
| < 0.5 | Awake  |
| > 0.5 | Sleepy |

###  Inference

Model predicts driver state **instantly** from a single image.


##  Sample Predictions

| Input            | Prediction |
| ---------------- | ---------- |
| Closed Eye Image | **Sleepy** |
| Open Eye Image   | **Awake**  |


  **Future Improvements**

* Real-time webcam integration
* Alert/Alarm system for drowsy detection
* Edge deployment (Raspberry Pi / Mobile)
* Full driver monitoring system integration



**CONCLUSION**

Transfer learning with MobileNetV2 significantly improved performance over the custom CNN while keeping the model lightweight and fast. This project demonstrates a strong foundation for **real-time driver safety systems**.


If you like this project, consider giving it a ⭐ on GitHub!
