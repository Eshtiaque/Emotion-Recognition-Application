# Speech Emotion Recognition (SER) using CNN, LSTM, and Hybrid Models

## 🌟 Overview

This project conducts a comparative study of three powerful Deep Learning architectures—**Convolutional Neural Network (CNN)**, **Long Short-Term Memory (LSTM)**, and **CNN-LSTM Hybrid** model—for recognizing emotion from speech using the **RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song)** dataset. Our objective was to determine the most effective combination of feature extraction (MFCC) and deep learning architecture for this task.

### Key Achievements:

✅ **CNN** Model achieved the highest **92.71% Accuracy**.
✅ Utilization of stacked **MFCC, Delta, and Delta-Delta** features.
✅ **Comprehensive performance comparison** of three distinct architectures.
✅ **Data Leakage Prevention:** Employed standard train-test splitting and validated using K-fold cross-validation principles.

### Live Demo & Resources

- 🌐 **Live Demo:** [[emotion-recognition](https://www.kaggle.com/code/eshtiaqueahmed/emotion-recognition)]
- 📊 **Dataset:** [[ravdess-emotional-speech-audio](https://www.kaggle.com/datasets/uwrfkaggler/ravdess-emotional-speech-audio)]

---

## 🚀 Key Features and Methodology

### 🔬 Feature Engineering (The Vocal Biomarkers)

We extracted **Mel-Frequency Cepstral Coefficients (MFCC)** from the audio files, treating them as a 2D feature map. To boost model performance, these features were stacked with **Delta ($\Delta$)** and **Delta-Delta ($\Delta\Delta$)** coefficients.

| Parameter | Value | Description |
| :--- | :--- | :--- |
| **Sampling Rate (SR)** | 22050 Hz | Audio sample rate used for feature extraction. |
| **N\_MFCC** | 40 | Number of MFCC coefficients. |
| **Feature Shape** | (120, 174, 1) | **Stacked (MFCC + $\Delta$ + $\Delta\Delta$):** (40*3, 174, 1) features by time frames. |
| **MAX\_PAD\_LEN** | 174 | Maximum time frames used for padding or truncation. |

### 🤖 Deep Learning Architectures

We compared three models, each designed for specific feature handling capabilities:

1.  **CNN:** Excellent for extracting **local, spectro-temporal patterns** from the 2D feature maps.
2.  **LSTM:** Best suited for analyzing **temporal (time-based) dependency** within the feature sequence.
3.  **CNN-LSTM Hybrid:** Uses **CNN layers for initial feature extraction** followed by **LSTM layers for sequential analysis**.

---

## 📈 Detailed Results and Comparison

The performance of our three models on the **Test Set** is compared below:

| Model | Accuracy | Precision (Weighted) | Recall (Weighted) | F1-Score (Weighted) | ROC-AUC (Weighted) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **CNN** | **92.7083%** | **93.2160%** | **92.7083%** | **92.6105%** | **99.5630%** |
| **LSTM** | 79.8611% | 80.3613% | 79.8611% | 79.9049% | 96.9948% |
| **CNN-LSTM** | 78.9931% | 79.5757% | 78.9931% | 79.0805% | 95.9652% |

### Key Findings:

* **Superior CNN Performance:** The **pure CNN** model achieved the best results across all key metrics, including Accuracy, F1-Score, and ROC-AUC.
* **Feature Robustness:** This experiment indicates that the **local 2D spectral properties** of the MFCC features (which the CNN excels at learning) are more critical for audio emotion recognition than the **long-term temporal sequence** (modeled by LSTM).
* **Hybrid Model Performance:** The **CNN-LSTM Hybrid** performed marginally worse than the standalone LSTM, suggesting that the complexity of the hybrid architecture did not yield performance benefits over the specialized CNN in this particular SER task.

---

## 📁 Dataset and Emotion Mapping

We utilized the **RAVDESS** dataset, which includes 8 distinct emotions:

| Emotion Code | Emotion Name |
| :--- | :--- |
| **01** | neutral |
| **02** | calm |
| **03** | happy |
| **04** | sad |
| **05** | angry |
| **06** | fearful |
| **07** | disgust |
| **08** | surprised |

---

## 👥 Authors

* [Eshtiaque Ahmed] - Lead Researcher - [Eshtiaque-Ahmed](https://github.com/Eshtiaque)]
* [Tasnia Washim] - Colead-Researcher - [Tasnia-washim](https://github.com/tasniawashim)]
* [Md Istihad Tamim] - Co-Researcher - [Istihad-Tamim](https://github.com/IstihadTamim318)]

**---**
