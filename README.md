# EEG Signal Filtering Using Temporal Convolutional Networks (TCN)

This project explores the application of Temporal Convolutional Networks (TCNs) to filter noisy electroencephalographic (EEG) signals. The approach replaces traditional signal filtering methods with a deep learning model that learns to approximate clean EEG signals directly from raw, noisy input.

## 🧠 Project Overview

EEG data is often contaminated by noise and artifacts such as muscle movements or eye blinks, making preprocessing essential. Traditional filtering techniques (e.g., FIR filters, ICA) require manual tuning and expert intervention. This project proposes a data-driven, end-to-end learning approach using TCNs.
	•	Input: raw EEG signal (1D, 501 time samples)
	•	Output: cleaned EEG signal (same shape)
	•	Architecture: deep TCN with 7 residual blocks
	•	Dataset: recorded in an EEG lab using a 256-channel EGI system
	•	Goal: automated EEG filtering for potential real-time BCI or clinical applications

## 🧪 Methodology
	•	Dataset: EEG signals collected at UMCS (Lublin) with a 256-channel EGI system.
	•	Training Data: 504 clean and 504 noisy epochs, each of length 501.
	•	Split: 80/20 train-test split with batches of size 32.
	•	Preprocessing: FIR-filtered vs raw signals via MNE-Python.
	•	Model: TCN implemented in PyTorch.
	•	Layers: [32, 64, 128, 128, 64, 32, 1]
	•	Activation: tanh
	•	Causal and dilated convolutions
	•	Loss: MSE
	•	Optimizer: Adam (lr=0.001)

## 📈 Results
	•	Final training loss: 0.0012 (MSE)
	•	Test loss: ~49 (MSE)
	•	Pearson correlation: ~75% between predicted and clean signals
	•	Qualitative results: Model preserves EEG periodicity and suppresses noise while mimicking some artifacts

## 🧩 Example Output
![result](https://github.com/user-attachments/assets/e0fc8a59-77ca-44e5-b36c-fc4dfaf3a63f)
