![Language](https://img.shields.io/badge/language-Python%20-blue.svg)
![License](https://img.shields.io/badge/License-MIT%20-red.svg)

# Modulation Classification

## Problem statement
  A synthetic dataset, generated with GNU Radio, consisting of 11 modulations.
  This is a variable-SNR dataset with moderate LO drift, light fading, and numerous
  different labeled SNR increments for use in measuring performance across
  different signal and noise power scenarios. It is required to train and compare
  three different models then try to combine and modify these architectures to
  obtain better results
## Combining Data
  The raw data contained of 2 channels mainly but we could apply derivative or
  integration on the data to get more channels.
  we have tried the following combinations during training:
  * Raw data
  * Raw data + derivative
  * Raw data + Integration
  Combining all three together won’t fit in RAM because size of data is large.
## Data explanation
  RadioML2016b data set consists of 1,200,000 samples each sample has the shape
  128x2 it represents 128 complex time domain samples with 2 vectors to represent
  the real and imaginary parts of the time samples.
  The dataset consists of 10 different signals each one has 20 different level of noise
  applied to it between -20 and 18 db Here’s example of each class with different
  db levels:
  - blue curve represents real values of the signal while magenta represents imaginary
  values.
  ## Different models
  We have built 4 models:
  * CNN
  * Vanilla RNN
  * LSTM
  * CNN-LSTM which is called CLDNN
 ## Tuning Techniques
  It was required to tune the learning rate of each model so we have tried the
  most used learning rates:
  * 1e-1
  * 1e-2
  * 1e-3
  * 1e-4
  * 1e-5
  * 1e-6
  
  In most models 1e-4 was the best regarding to accuracy and loss but in LSTM
  model the default settings of Adam optimizer were better in integral model.
  We also used some callback function to optimize the tuning process.
  * EarlyStopping to stop training if the model didn’t enhance accuracy for 5
  epochs
  * Save checkpoint which saves a checkpoint only if the model has enhanced
  its accuracy
