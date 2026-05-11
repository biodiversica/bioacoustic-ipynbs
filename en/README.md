# Bioacoustic Notebooks

Interactive Jupyter notebooks for bioacoustic analysis of field recordings.

---

## 📊 Notebooks

### 1. Google Drive Audio Analyzer
**Analyze audio from Google Drive with any neural network model**

- Load audio files directly from your Google Drive
- Run a neural network model (BirdNET, Perch, or custom) on all recordings
- Supports multiple recording sites (organized as subfolders)
- Save detection results as CSV files
- Configurable confidence threshold and preprocessing options

🔗 **Open in Colab:**
- [`googledrive_audio_analyzer.ipynb`](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_audio_analyzer.ipynb)

---

### 2. Google Drive BirdNET Analyzer
**Specialized notebook for BirdNET model from Google Drive**

- Pre-configured for BirdNET (world's most popular bird song detector)
- Load BirdNET automatically from HuggingFace
- Faster setup with default parameters for BirdNET
- All features of the general audio analyzer

🔗 **Open in Colab:**
- [`googledrive_birdnet_analyzer.ipynb`](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_birdnet_analyzer.ipynb)

---

### 3. Arbimon Audio Analyzer
**Analyze audio directly from your Arbimon project with any classification model**

- Connect to your Arbimon account and access your audio library
- Run neural network models on Arbimon recordings
- Automatic datetime parsing from Arbimon metadata
- Save results back to Google Drive for visualization
- No need to download audio files — analyze in place

🔗 **Open in Colab:**
- [`arbimon_audio_analyzer.ipynb`](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_audio_analyzer.ipynb)

---

### 4. Arbimon BirdNET Analyzer
**Specialized notebook for BirdNET model with Arbimon**

- Pre-configured for BirdNET on Arbimon recordings
- Connect to Arbimon and automatically detect bird species
- No manual audio download required
- All features of the general Arbimon analyzer

🔗 **Open in Colab:**
- [`arbimon_birdnet_analyzer.ipynb`](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_birdnet_analyzer.ipynb)

---

### 5. Classification Results Analyzer
**Post-process, visualize, and review detection results**

- Load results from any audio classification tool (CSV or TXT format)
- Merge multiple result files automatically
- Generate publication-ready plots:
  - Species × site heatmaps
  - Confidence vs. time scatter plots
  - Species richness bar charts
  - Species activity by hour of day
- Extract audio clips for each detection
- Interactive web-based segment reviewer with spectrogram viewer

🔗 **Open in Colab:**
- [`classification_results_analyzer.ipynb`](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/classification_results_analyzer.ipynb)

---

## Getting Started

1. **Choose a notebook** based on your audio source:
   - Google Drive → use Google Drive notebooks
   - Arbimon → use Arbimon notebooks

2. **Choose a model**:
   - BirdNET → use specialized BirdNET notebooks (faster setup)
   - Other model → use general Audio Analyzer notebooks

3. **Run in Colab**: Click the link above, no installation needed

4. **Follow the steps**: Each notebook has clear step-by-step instructions

---

## Requirements

- **Google account** (for Google Drive and Colab)
- **Google Drive folder** with audio files (or Arbimon account for Arbimon notebooks)
- **Model file** (`.tflite` or `.onnx`) and **labels file** (`.txt`)
  - BirdNET is downloaded automatically from HuggingFace

---

## Supported Audio Formats

- WAV (`.wav`)
- FLAC (`.flac`)
- MP3 (`.mp3`)

---

## Supported Models

- **BirdNET** — global bird species detector (recommended)
- **Google Perch** — advanced bird audio classification
- **Custom TFLite models** — any `.tflite` model you have trained
- **Custom ONNX models** — any `.onnx` model you have trained

---

## Output

### From Audio Analyzers
CSV files with detections:
- Site, date, time, recording timestamp
- Species label and confidence score
- Start/end time within the recording
- Optional: site coordinates

### From Results Analyzer
- High-resolution PNG plots (heatmaps, scatter plots, bar charts)
- Extracted audio clips (`.wav` files) for each detection
- Classification review with spectrograms (true/false labels)

---

## Support & Feedback

For issues, questions, or feedback, visit [biodiversica.xyz](https://biodiversica.xyz).

---

Back to [main README](../README.md)
