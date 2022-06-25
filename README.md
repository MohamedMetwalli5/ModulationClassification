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
