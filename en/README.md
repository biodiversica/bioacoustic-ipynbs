# Bioacoustic Notebooks

Interactive Jupyter notebooks for bioacoustic analysis of field recordings.

---

## 📊 Notebooks

### 1. Google Drive Audio Analyzer
**Analyze audio from Google Drive with any neural network model**

- Load audio files directly from your Google Drive
- Run a neural network model (BirdNET, Perch, or custom) on all recordings
- Supports multiple recording sites (organized as subfolders)
- Save detection results as one CSV per recording, then merge them into a single CSV
- Configurable confidence threshold and preprocessing options

📓 **File:** [`googledrive_audio_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_audio_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_audio_analyzer.ipynb)

---

### 2. Google Drive BirdNET Analyzer
**Specialized notebook for BirdNET model from Google Drive**

- Pre-configured for BirdNET (world's most popular bird song detector)
- Load BirdNET automatically from HuggingFace
- Faster setup with default parameters for BirdNET
- All features of the general audio analyzer

📓 **File:** [`googledrive_birdnet_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_birdnet_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_birdnet_analyzer.ipynb)

---

### 3. Arbimon Audio Analyzer
**Analyze audio directly from your Arbimon project with any classification model**

- Connect to your Arbimon account and access your audio library
- Run neural network models on Arbimon recordings
- Automatic datetime parsing from Arbimon metadata
- Save results back to Google Drive for visualization, merged into a single CSV
- No need to download audio files — analyze in place

📓 **File:** [`arbimon_audio_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_audio_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_audio_analyzer.ipynb)

---

### 4. Arbimon BirdNET Analyzer
**Specialized notebook for BirdNET model with Arbimon**

- Pre-configured for BirdNET on Arbimon recordings
- Connect to Arbimon and automatically detect bird species
- No manual audio download required
- All features of the general Arbimon analyzer

📓 **File:** [`arbimon_birdnet_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_birdnet_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_birdnet_analyzer.ipynb)

---

### 5. Classification Results Analyzer
**Post-process, visualize, and review detection results**

- Load results from any audio classification tool (CSV or TXT format), from a folder of result files **or** a single merged CSV
- Merge multiple result files automatically
- Generate publication-ready plots:
  - Species × site heatmaps
  - Confidence vs. time scatter plots
  - Species richness bar charts
  - Species activity by hour of day
- Extract audio clips for each detection
- Interactive web-based segment reviewer with spectrogram viewer

📓 **File:** [`classification_results_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/classification_results_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/classification_results_analyzer.ipynb)

---

## 🧬 Embeddings Pipeline

The three notebooks below form an optional two-stage workflow: compute embeddings once with a foundation-model backbone, then classify (or search) them many times without re-running the heavy backbone.

### 6. Compute Embeddings Database
**Extract reusable audio embeddings from a foundation model backbone**

- Read audio from Google Drive or an Arbimon project
- Load a backbone model from HuggingFace (Perch v2, BirdNET, or custom ONNX)
- Compute one embedding per audio segment and store them in a SQLite `*.embeddings.db` file
- Embeddings are computed once and reused by the two notebooks below

📓 **File:** [`compute_embeddings_database.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/compute_embeddings_database.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/compute_embeddings_database.ipynb)

---

### 7. Audio Classification from Embeddings
**Run a lightweight classifier head over a pre-computed embeddings database**

- Apply an ONNX or TFLite classifier head on top of stored embeddings (no backbone re-run)
- Search a single `.db` file or a whole folder of them in one run
- Resumable: one result file per recording, so a crashed Colab run picks up where it stopped
- Merge all per-recording results into a single CSV ready for the Results Analyzer

📓 **File:** [`audio_classification_from_embeddings.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/audio_classification_from_embeddings.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/audio_classification_from_embeddings.ipynb)

---

### 8. Embeddings Database Vector Search
**Find audio that sounds like your example clips — no trained classifier required**

- Provide a few short example clips ("templates"); each filename (or subfolder) becomes a label
- Compute a template embedding per clip, then run a vector similarity search against one or more embeddings databases
- Tune Top-K, similarity metric (cosine / dot / euclidean), and score threshold
- Extract and review the matching audio segments — all within the same notebook

📓 **File:** [`embeddings_db_vector_search.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/embeddings_db_vector_search.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/embeddings_db_vector_search.ipynb)

---

## Getting Started

1. **Choose a notebook** based on your audio source:
   - Google Drive → use Google Drive notebooks
   - Arbimon → use Arbimon notebooks

2. **Choose a model**:
   - BirdNET → use specialized BirdNET notebooks (faster setup)
   - Other model → use general Audio Analyzer notebooks

3. **Open the notebook**:
   - Click the notebook link to view it on GitHub
   - Click the "Open in Colab" button (in GitHub) or copy to your local Jupyter

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
CSV files with detections (one per recording, plus a single merged CSV):
- Site, date, time, recording timestamp
- Species label and confidence score
- Start/end time within the recording
- Optional: site coordinates

### From the Embeddings Pipeline
- A reusable SQLite `*.embeddings.db` database (Compute Embeddings Database)
- Detection CSVs from a classifier head (Audio Classification from Embeddings)
- Similarity-match CSVs and extracted/reviewed clips (Embeddings Database Vector Search)

### From Results Analyzer
- High-resolution PNG plots (heatmaps, scatter plots, bar charts)
- Extracted audio clips (`.wav` files) for each detection
- Classification review with spectrograms (true/false labels)

---

## Support & Feedback

For issues, questions, or feedback, visit [biodiversica.xyz](https://biodiversica.xyz).

---

Back to [main README](../README.md)
