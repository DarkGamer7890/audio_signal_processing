# Audio_signal_processing: FM Simulation, Noise Reduction, Speaker Recognition
This repository contains a comprehensive audio-signal proces
sing notebook that integrates three major capabilities:

- 🎧 FM Simulation — Modulation, demodulation, filtering, and spectrum analysis

- 🔇 Noise Reduction — Using FFT filtering and a Recurrent Neural Network (RNN)

- 🧠 Speaker Recognition — Deep-learning-based classification using spectrogram features

The project serves as a combined DSP + Machine Learning lab for experimentation, education, and research.

## 📁 Project Structure
```
DC_DL.ipynb          # Main notebook combining all modules
dataset/             # Speaker audio dataset (user-provided)
models/              # Saved RNN and CNN weights (optional)
outputs/             # Plots, denoised audio, checkpoints
```

### 🔧 Features Overview
## 1️⃣ FM Simulation

- Audio signal loading and visualization

- Wideband FM modulation

- AWGN noise channel simulation

- FM demodulation with Hilbert transform

- Butterworth low-pass filtering

- Spectrum, spectrogram & audio-playback utilities


## 2️⃣ Noise Reduction (FFT + RNN)

Two denoising pipelines are implemented:

### FFT-Based Noise Reduction

- Converts noisy waveform to frequency domain

- Thresholds or masks noisy components

- Reconstructs denoised waveform using iFFT

- Visualizes clean vs noisy spectra

### RNN-Based Noise Reduction

- Sequence-to-sequence audio denoising

- Uses an RNN (e.g., LSTM/GRU) trained on noisy/clean pairs

- Produces smoother and more natural denoised output

- Can be extended for real-time streaming applications

## 3️⃣ Speaker Recognition (Deep Learning)

- Mel-spectrogram feature extraction

- Dataset loading for multiple speakers

- Custom CNN classifier

- Training, validation, and testing loops

- Accuracy curves + confusion matrix

- Inference function to predict speaker identity

## 📦 Dependencies

Install directly:
```
pip install numpy scipy matplotlib soundfile sounddevice librosa torchaudio torch torchvision ipywidgets
```

## 🚀 How to Use
# FM Simulation

Run the FM cells to:
```
Load the audio

Modulate → Add noise → Demodulate

Visualize time/frequency plots

Listen to recovered audio
```
# Noise Reduction

Use:
```
fft_denoise() for spectrum-based cleaning

rnn_denoise() once the model is trained
```
Outputs include:

Cleaned waveforms
```
Spectrogram comparison

Save-to-disk options
```
# Speaker Recognition

1. Place dataset in labeled folders:
 ```
dataset/
   speaker1/
   speaker2/
   ...
 ```
2. Train the CNN model using provided training loop

3. Use:
```
predict_speaker_from_checkpoint("model.pth", "audio.wav")
```
  to identify a speaker

## 📊 Visualizations & Outputs

The notebook generates:
```
- Spectrograms

- FFT plots

- Denoising comparisons

- Training/validation curves

- Confusion matrix

- Audio playback (clean, noisy, denoised)
```

## 📝 Notes

- Designed for use in local Python or Google Colab

- Modules are modular and can be separated into standalone scripts

- Extendable to:
```
- NBFM
- Larger RNN architectures (GRU/LSTM/TCN)
- Transformer-based speaker recognition
```

