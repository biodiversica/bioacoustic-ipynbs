# Interactive notebooks for Bioacoustics applications

---

## 📊 Audio Analysis

### 1. Audio Analysis in Google Drive using Classification Models
This notebook accesses audio recordings directly in your **Google Drive** to run a **Neural Network Classification Model** and detect specific species in each recording.

- Load audio files directly from your Google Drive
- Run a neural network model (BirdNET, Perch, or custom) on all recordings
- Supports multiple recording sites (organized as subfolders)

📓 **File:** [`googledrive_audio_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_audio_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_audio_analyzer.ipynb)

---

### 2. Audio Analysis in Google Drive using BirdNET
This notebook accesses audio recordings directly in your **Google Drive** to run **BirdNET v2.4** and detect species in each recording.

- Load audio files directly from your Google Drive
- Pre-configured to use BirdNET (bird sound classifier)
- Supports multiple recording sites (organized as subfolders)

📓 **File:** [`googledrive_birdnet_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_birdnet_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/googledrive_birdnet_analyzer.ipynb)

---

### 3. Audio Analysis in Arbimon Projects using Classification Models
This notebook downloads recordings from your **Arbimon** projects to run an external **Neural Network Classification Model** and detect specific species in each recording.

- Connect to your Arbimon account and access your audio library
- Run neural network models on Arbimon recordings
- Automatic datetime parsing from Arbimon metadata
- No manual audio download required
- Save results to Google Drive for visualization

📓 **File:** [`arbimon_audio_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_audio_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_audio_analyzer.ipynb)

---

### 4. Audio Analysis in Arbimon Projects using BirdNET
This notebook accesses recordings from your **Arbimon** projects to run **BirdNET v2.4** and detect species in each recording.

- Pre-configured for BirdNET on Arbimon recordings
- Connect to Arbimon and automatically detect bird species
- Automatic datetime parsing from Arbimon metadata
- No manual audio download required
- Save results to Google Drive for visualization


📓 **File:** [`arbimon_birdnet_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_birdnet_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/arbimon_birdnet_analyzer.ipynb)

---

### 5. Classification Results Analysis (Post-Processing and Visualization)
This notebook accesses audio classification results, generates plots, and extracts audio segments for the detections of interest.

- Access results obtained through the audio analysis notebooks
- Generate plots from the results
- Extract audio segments for each detection
- Interactive reviewer with spectrogram viewer

📓 **File:** [`classification_results_analyzer.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/classification_results_analyzer.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/classification_results_analyzer.ipynb)

---

## 📊 Using Embeddings

### 6. Creating Embeddings Databases
This notebook extracts the **embeddings** produced by a model and saves them in a **SQLite database** on your Google Drive.

- Access audio from Google Drive or an Arbimon project
- Load a backbone from HuggingFace (Perch v2, BirdNET, or custom ONNX)
- Extract embeddings from audio segments and store them in a SQLite database
- Embeddings are extracted once and reused by notebooks 7 and 8

📓 **File:** [`compute_embeddings_database.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/compute_embeddings_database.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/compute_embeddings_database.ipynb)

---

### 7. Audio Classification from Embeddings
This notebook classifies audio recordings by applying a **classifier model** over pre-computed embeddings stored in a SQLite database.

- Apply a classifier (ONNX or TFLite format) over the stored embeddings (without running the *backbone*, which makes the process much faster)
- Analyze a single database or a folder with multiple databases
- Save results to Google Drive in the same format as the audio analysis notebooks

📓 **File:** [`audio_classification_from_embeddings.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/audio_classification_from_embeddings.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/audio_classification_from_embeddings.ipynb)

---

### 8. Vector Search in Embeddings Databases
This notebook finds audio segments that are **similar to pre-selected audio templates**, by comparing the templates against **embeddings available in databases**.

- Provide a few audio templates; each filename (or subfolder) becomes a label
- Extract one embedding per template and run a vector similarity search against one or more embeddings databases
- Tune Top-K, similarity metric (cosine / dot / euclidean), and score threshold
- Extract and review the matching audio segments — all within the same notebook

📓 **File:** [`embeddings_db_vector_search.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/en/embeddings_db_vector_search.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/en/embeddings_db_vector_search.ipynb)

---
