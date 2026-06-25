# Notebooks interativos para aplicações em Bioacústica

---

## 📊 Análise de Áudio

### 1. Análise de Áudios no Google Drive utilizando Modelos de Classificação
Este notebook acessa gravações de áudio diretamente no seu **Google Drive** para executar um **Modelo de Classificação por Rede Neural** e detectar espécies específicas em cada gravação.

- Carregue arquivos de áudio diretamente do seu Google Drive
- Execute um modelo de rede neural (BirdNET, Perch ou customizado) em todas as gravações
- Suporta múltiplos pontos de amostragem (organizados em subpastas)

📓 **Arquivo:** [`googledrive_audio_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/googledrive_audio_analyzer_pt-BR.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/googledrive_audio_analyzer_pt-BR.ipynb)

---

### 2. Análise de Áudios no Google Drive utilizando o BirdNET
Este notebook acessa gravações de áudio diretamente no seu **Google Drive** para executar o **BirdNET v2.4** e detectar espécies em cada gravação.

- Carregue arquivos de áudio diretamente do seu Google Drive
- Pré-configurado para utilização do BirdNET (classificador de sons de aves)
- Suporta múltiplos pontos de amostragem (organizados em subpastas)

📓 **Arquivo:** [`googledrive_birdnet_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/googledrive_birdnet_analyzer_pt-BR.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/googledrive_birdnet_analyzer_pt-BR.ipynb)

---

### 3. Análise de Áudios em Projetos do Arbimon utilizando Modelos de Classificação
Este notebook baixa gravações dos seus projetos no **Arbimon** para executar um **Modelo de Classificação por Rede Neural** externo e detectar espécies específicas em cada gravação.

- Conecte à sua conta Arbimon e acesse sua biblioteca de áudio
- Execute modelos de rede neural em gravações do Arbimon
- Análise automática de data/hora a partir dos metadados do Arbimon
- Nenhum download manual de áudio necessário
- Salve resultados no Google Drive para visualização

📓 **Arquivo:** [`arbimon_audio_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/arbimon_audio_analyzer_pt-BR.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/arbimon_audio_analyzer_pt-BR.ipynb)

---

### 4. Análise de Áudios em Projetos do Arbimon utilizando o BirdNET
Este notebook acessa gravações dos seus projetos no **Arbimon** para executar o **BirdNET v2.4** e detectar espécies em cada gravação.

- Pré-configurado para BirdNET em gravações do Arbimon
- Conecte ao Arbimon e detecte automaticamente espécies de aves
- Análise automática de data/hora a partir dos metadados do Arbimon
- Nenhum download manual de áudio necessário
- Salve resultados no Google Drive para visualização


📓 **Arquivo:** [`arbimon_birdnet_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/arbimon_birdnet_analyzer_pt-BR.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/arbimon_birdnet_analyzer_pt-BR.ipynb)

---

### 5. Análise dos Resultados de Classificação (Pós-Processamento e Visualização)
Este notebook acessa resultados de classificação de áudio, gera gráficos e extrai segmentos de áudio para as detecções de interesse.

- Acesso resultados obtidos através dos notebooks de análise de áudio
- Gere gráficos com os resultados
- Extraia segmentos de áudio para cada detecção
- Revisor interativo com visualizador de espectrograma

📓 **Arquivo:** [`classification_results_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/classification_results_analyzer_pt-BR.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/classification_results_analyzer_pt-BR.ipynb)

---

## 📊 Utilização de Embeddings

### 6. Criação de Bancos de Dados (*Databases*) de Embeddings
Este notebook extrai os **embeddings** como resultados de um modelo e os salva em um **banco de dados SQLite** no seu Google Drive.

- Acesse áudios do Google Drive ou de um projeto do Arbimon
- Carregue um backbone do HuggingFace (Perch v2, BirdNET ou ONNX customizado)
- Extraia embeddings de segmentos de áudio e armazene em uma database SQLite 
- Os embeddings são extraídos uma vez e reutilizados pelos notebooks 7 e 8

📓 **Arquivo:** [`compute_embeddings_database_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/compute_embeddings_database_pt-BR.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/compute_embeddings_database_pt-BR.ipynb)

---

### 7. Classificação de Áudio a partir de Embeddings
Este notebook classifica gravações de áudio aplicando um **modelo classificador** sobre embeddings pré-computados armazenados em um banco de dados SQLite.

- Aplique um classificador (formato ONNX ou TFLite) sobre os embeddings armazenados (sem executar o *backbone*, o que torna o processo muito mais rápido)
- Analise uma única database ou uma pasta com múltiplas bases de dados
- Salve resultados no Google Drive no mesmo formato dos notebooks de análise de áudio

📓 **Arquivo:** [`audio_classification_from_embeddings_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/audio_classification_from_embeddings_pt-BR.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/audio_classification_from_embeddings_pt-BR.ipynb)

---

### 8. Busca Vetorial (*Vector Search*) em Bancos de Dados (*Databases*) de Embeddings
Este notebook encontra segmentos de áudio que **possuam similaridade com templates de áudios pré-selecionados**, através da comparação dos templates com **embeddings disponíveis em bancos de dados**.

- Forneça alguns templates de áudio; cada nome de arquivo (ou subpasta) vira um rótulo
- Extraia um embedding por template e execute uma busca vetorial por similaridade em um ou mais bancos de embeddings
- Ajuste Top-K, métrica de similaridade (cosine / dot / euclidean) e limiar de score
- Extraia e revise os segmentos de áudio correspondentes — tudo no mesmo notebook

📓 **Arquivo:** [`embeddings_db_vector_search_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/embeddings_db_vector_search_pt-BR.ipynb)
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/embeddings_db_vector_search_pt-BR.ipynb)

---

