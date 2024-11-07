# Anomaly Detection in Industrial Sound

## Overview
This project addresses the challenge of detecting anomalous sounds in an industrial environment. The objective is to identify anomalies by analyzing sounds from a specific type of machine using only normal sound samples during training. Anomalous sound detection plays a crucial role in maintaining machine efficiency and preventing malfunctions.

## Dataset
The data used for this project consists of audio samples from the **ToyADMOS** and **MIMII** datasets, focusing on *slide rail machines*. The dataset is divided into:
- **Development Dataset:** Contains 2,370 normal training samples and 1,101 test samples (including normal and anomalous samples).
- **Evaluation Dataset:** Consists of 2,370 normal training samples and 834 unlabeled test samples.

## Data Preprocessing
Multiple preprocessing methods were used to enhance feature extraction from audio samples, including:
1. **Fourier Transform:** For frequency analysis of audio samples.
2. **Log Mel Spectrogram:** For combining time and frequency information.
3. **Normalization:** Standardizing data to improve model convergence.
4. **Mel-Frequency Cepstral Coefficients (MFCC):** For compressing the frequency spectrum.

## Models
Two main models were evaluated:
- **Autoencoder:** Trained to reconstruct normal sounds and detect anomalies by measuring reconstruction error.
- **Gaussian Mixture Model (GMM):** Trained to model normal data distribution and detect anomalies through log-likelihood scores.

### Model Selection
Different configurations were tested to optimize each model's performance. The autoencoder's bottleneck size and GMM parameters were carefully tuned to achieve the best results.

## Results
The **GMM** model outperformed the autoencoder with an **AUC of 0.9234** versus the autoencoder's **0.8997**. The performance of the autoencoder varied across machines, with Machine 02 proving the most challenging.

## Conclusion
The project demonstrated the efficacy of the GMM for this anomaly detection task. However, improvements could include employing domain adaptation techniques to handle data variability across machines and refining feature selection to bridge the domain gap.
