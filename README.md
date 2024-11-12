# Cardiac Arrhythmia Detection Using Likelihood Ratio-Based Out-of-Distribution Detection

This project presents a deep learning approach for detecting cardiac arrhythmias in ECG data using a likelihood ratio-based out-of-distribution (OOD) detection method. The system is designed to classify time-series ECG signals as normal or abnormal by leveraging log-likelihood ratios between a main model and a background model, enhancing the accuracy of arrhythmia detection.


## Overview
Cardiac arrhythmias can be life-threatening if not detected early. This project implements a likelihood ratio-based OOD detection on ECG time-series data to identify arrhythmic patterns, contributing to non-invasive and timely diagnostics. 

The model:
- Uses an LSTM-based architecture trained on the MIT-BIH Arrhythmia Database.
- Computes the log-likelihood ratio between normal ECG signals and a background model for abnormal signals.
- Classifies test samples as normal or abnormal based on the LLR threshold.

## Dataset
This project utilizes the MIT-BIH Arrhythmia Database, which contains 48 ECG recordings collected from 47 patients.

### Dataset Details:
- **Source**: Beth Israel Deaconess Medical Center (Boston, MA), 1975-1979.
- **Sampling Rate**: 360 Hz (360 data points per second).
- **Format**: CSV files with time-series ECG data.
- **Columns**:
  - **Index**: Data point index.
  - **Elapsed Time (ms)**: Time reference.
  - **MLII Lead**: Main ECG lead used for arrhythmia detection.
  - **Secondary Lead**: Additional lead, varying by record.


## Methodology
The detection system is based on an optimized LSTM model to classify ECG signals. The methodology includes:
1. **Data Loading and Preprocessing**: Signals are normalized for consistency.
2. **Model Architecture**: 
   - Main LSTM model for normal signals.
   - Background LSTM model trained for likelihood comparison.
3. **Training and Validation**: 
   - Training on normal ECG data.
   - Early stopping and learning rate scheduling for optimal performance.
4. **Log-Likelihood Ratio (LLR) Computation**:
   - LLR values are calculated using the mean squared error (MSE) between predicted and actual signals for both models.
   - A threshold is applied to distinguish between normal and abnormal signals.
5. **Evaluation Metrics**: Accuracy, recall, F1 score, and confusion matrix are computed.


