# Notebooks para Bioacústica

Notebooks Jupyter interativos para análise bioacústica de gravações de campo.

---

## 📊 Notebooks

### 1. Google Drive Audio Analyzer
**Analise áudio do Google Drive com qualquer modelo neural**

- Carregue arquivos de áudio diretamente do seu Google Drive
- Execute um modelo de rede neural (BirdNET, Perch ou customizado) em todas as gravações
- Suporta múltiplos pontos de amostragem (organizados em subpastas)
- Salve os resultados como um CSV por gravação e depois mescle tudo em um único CSV
- Limiar de confiança configurável e opções de pré-processamento

📓 **Arquivo:** [`googledrive_audio_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/googledrive_audio_analyzer_pt-BR.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/googledrive_audio_analyzer_pt-BR.ipynb)

---

### 2. Google Drive BirdNET Analyzer
**Notebook especializado para modelo BirdNET do Google Drive**

- Pré-configurado para BirdNET (classificador de sons de aves)
- Carregue BirdNET automaticamente do HuggingFace
- Configuração mais rápida com parâmetros padrão para BirdNET
- Todos os recursos do analisador de áudio geral

📓 **Arquivo:** [`googledrive_birdnet_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/googledrive_birdnet_analyzer_pt-BR.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/googledrive_birdnet_analyzer_pt-BR.ipynb)

---

### 3. Arbimon Audio Analyzer
**Analise áudio diretamente do seu projeto Arbimon com qualquer modelo de classificação**

- Conecte à sua conta Arbimon e acesse sua biblioteca de áudio
- Execute modelos de rede neural em gravações do Arbimon
- Análise automática de data/hora a partir dos metadados do Arbimon
- Salve resultados no Google Drive para visualização, mesclados em um único CSV
- Sem necessidade de baixar arquivos de áudio — analise no lugar

📓 **Arquivo:** [`arbimon_audio_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/arbimon_audio_analyzer_pt-BR.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/arbimon_audio_analyzer_pt-BR.ipynb)

---

### 4. Arbimon BirdNET Analyzer
**Notebook especializado para modelo BirdNET com Arbimon**

- Pré-configurado para BirdNET em gravações do Arbimon
- Conecte ao Arbimon e detecte automaticamente espécies de aves
- Nenhum download manual de áudio necessário
- Todos os recursos do analisador geral de Arbimon

📓 **Arquivo:** [`arbimon_birdnet_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/arbimon_birdnet_analyzer_pt-BR.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/arbimon_birdnet_analyzer_pt-BR.ipynb)

---

### 5. Classification Results Analyzer
**Pós-processe, visualize e revise resultados de detecção**

- Carregue resultados de qualquer ferramenta de classificação de áudio (formato CSV ou TXT), de uma pasta de arquivos **ou** de um único CSV mesclado
- Mescle múltiplos arquivos de resultados automaticamente
- Gere gráficos prontos para publicação:
  - Mapas de calor espécie × ponto
  - Gráficos de dispersão confiança vs. tempo
  - Gráficos de barras de riqueza de espécies
  - Atividade de espécie por hora do dia
- Extraia clipes de áudio para cada detecção
- Revisor interativo baseado na web com visualizador de espectrograma

📓 **Arquivo:** [`classification_results_analyzer_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/classification_results_analyzer_pt-BR.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/classification_results_analyzer_pt-BR.ipynb)

---

## 🧬 Pipeline de Embeddings

Os três notebooks abaixo formam um fluxo opcional em dois estágios: calcule os embeddings uma vez com um backbone de modelo de fundação e depois classifique (ou faça buscas) neles várias vezes, sem reexecutar o backbone pesado.

### 6. Compute Embeddings Database
**Extraia embeddings de áudio reutilizáveis a partir de um backbone de modelo de fundação**

- Leia áudio do Google Drive ou de um projeto Arbimon
- Carregue um backbone do HuggingFace (Perch v2, BirdNET ou ONNX customizado)
- Calcule um embedding por segmento de áudio e os armazene em um arquivo SQLite `*.embeddings.db`
- Os embeddings são calculados uma vez e reutilizados pelos dois notebooks abaixo

📓 **Arquivo:** [`compute_embeddings_database_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/compute_embeddings_database_pt-BR.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/compute_embeddings_database_pt-BR.ipynb)

---

### 7. Audio Classification from Embeddings
**Execute um classificador leve sobre um banco de embeddings pré-computado**

- Aplique um classificador ONNX ou TFLite sobre os embeddings armazenados (sem reexecutar o backbone)
- Busque em um único arquivo `.db` ou em uma pasta inteira deles em uma única execução
- Retomável: um arquivo de resultado por gravação, então uma execução interrompida do Colab continua de onde parou
- Mescle todos os resultados por gravação em um único CSV pronto para o Results Analyzer

📓 **Arquivo:** [`audio_classification_from_embeddings_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/audio_classification_from_embeddings_pt-BR.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/audio_classification_from_embeddings_pt-BR.ipynb)

---

### 8. Embeddings Database Vector Search
**Encontre áudio que soa como seus clipes de exemplo — sem necessidade de classificador treinado**

- Forneça alguns clipes de exemplo curtos ("templates"); cada nome de arquivo (ou subpasta) vira um rótulo
- Calcule um embedding por template e execute uma busca vetorial por similaridade contra um ou mais bancos de embeddings
- Ajuste Top-K, métrica de similaridade (cosine / dot / euclidean) e limiar de escore
- Extraia e revise os segmentos de áudio correspondentes — tudo no mesmo notebook

📓 **Arquivo:** [`embeddings_db_vector_search_pt-BR.ipynb`](https://github.com/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/embeddings_db_vector_search_pt-BR.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/biodiversica/bioacoustic-ipynbs/blob/master/pt-BR/embeddings_db_vector_search_pt-BR.ipynb)

---

## Começando

1. **Escolha um notebook** com base em sua fonte de áudio:
   - Google Drive → use notebooks do Google Drive
   - Arbimon → use notebooks do Arbimon

2. **Escolha um modelo**:
   - BirdNET → use notebooks BirdNET especializados (configuração mais rápida)
   - Outro modelo → use notebooks gerais de Audio Analyzer

3. **Abra o notebook**:
   - Clique no link do notebook para visualizá-lo no GitHub
   - Clique no botão "Open in Colab" (no GitHub) ou copie para seu Jupyter local

4. **Siga os passos**: Cada notebook tem instruções claras passo a passo

---

## Requisitos

- **Conta Google** (para Google Drive e Colab)
- **Pasta no Google Drive** com arquivos de áudio (ou conta Arbimon para notebooks Arbimon)
- **Arquivo de modelo** (`.tflite` ou `.onnx`) e **arquivo de rótulos** (`.txt`)
  - BirdNET é baixado automaticamente do HuggingFace

---

## Formatos de Áudio Suportados

- WAV (`.wav`)
- FLAC (`.flac`)
- MP3 (`.mp3`)

---

## Modelos Suportados

- **BirdNET** — detector global de espécies de aves (recomendado)
- **Google Perch** — classificação avançada de áudio de aves
- **Modelos TFLite customizados** — qualquer modelo `.tflite` que você tenha treinado
- **Modelos ONNX customizados** — qualquer modelo `.onnx` que você tenha treinado

---

## Saída

### De Audio Analyzers
Arquivos CSV com detecções (um por gravação, mais um único CSV mesclado):
- Ponto, data, hora, marca de tempo da gravação
- Rótulo e escore de confiança da espécie
- Tempo de início/fim dentro da gravação
- Opcional: coordenadas do ponto

### Do Pipeline de Embeddings
- Um banco de dados SQLite `*.embeddings.db` reutilizável (Compute Embeddings Database)
- CSVs de detecção de um classificador (Audio Classification from Embeddings)
- CSVs de correspondências por similaridade e clipes extraídos/revisados (Embeddings Database Vector Search)

### De Results Analyzer
- Gráficos PNG de alta resolução (mapas de calor, gráficos de dispersão, gráficos de barras)
- Clipes de áudio extraídos (`.wav`) para cada detecção
- Revisão de classificação com espectrogramas (rótulos verdadeiro/falso)

---

## Suporte e Feedback

Para problemas, dúvidas ou feedback, visite [biodiversica.xyz](https://biodiversica.xyz).

---

Voltar para [README principal](../README.md)
