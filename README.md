# Time-Series Prediction with Neural Networks

## Introduction
This repository contains the code and data for a project focused on predicting time-series data. The data is synthetic, derived from sinusoidal signals with added noise, and transformed into a tabular format suitable for machine learning models.

### Data Description
The dataset is composed of time-series data representing different 'eras' that correspond to changes in the underlying distribution of the signal's frequency and amplitude. Each row in the dataset represents a time-step, and the columns include various features that describe recent temporal behavior.

### Task
The primary task is to predict the `target_10_val` label for the most recent day, with the assumption that the labels for that day are unknown. The data arrives in two forms:
- **Sequential 'day-wise':** All data for a given day is received, followed by all data for the subsequent day.
- **Row-wise:** Data arrives one row at a time, allowing for model updates based on the most recent information.

## Models
The goal is to apply and compare different neural network architectures for the task. Below is the list of models we have tried:

### 1. Long Short-Term Memory (LSTM) Network
- **File:** `LSTM.ipynb`
- **Description:**
  The LSTM network is a type of recurrent neural network that is capable of learning order dependence in sequence prediction problems. This is crucial in our task since the data is sequential and the prediction for a given time-step can depend on the previous data points.
  
  The LSTM model is designed to avoid the long-term dependency problem, allowing it to remember information for long periods. The basic unit of an LSTM is the cell, which contains mechanisms called gates that regulate the flow of information in and out of the cell.
  
  The LSTM model in `LSTM.ipynb` processes the data sequentially, taking into account the temporal dependencies within the input features. Early stopping is implemented to halt training if the validation accuracy does not improve for 3 epochs, preventing overfitting.

### Results
The repository contains results for datasets with and without noise:
- **With Noise:** Provides a more challenging scenario and tests the robustness of the models.
- **Without Noise:** Allows the models to learn from a cleaner signal, often resulting in better prediction accuracy.

Each file (`cf_train.csv` and `cf_train_no_noise.csv`) corresponds to these two scenarios. The results are documented within the respective Jupyter notebooks for each model tested.

## License
This project is open-sourced under the [MIT license](LICENSE.md).

