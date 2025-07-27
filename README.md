# TextMineML

This project implements a complete text‑mining pipeline over academic articles gathered from various sources.

## 🔁 Current Workflow

1. **Data Collection & Preprocessing**  
   - Web scraping from the UPCH repository (https://repositorio.upch.edu.pe) via the notebook `01_Translation_y_scraping.ipynb`  
   - Manual translation review of German passages using `02_find_no_translated.ipynb`  
   - Text cleaning (lowercasing, punctuation removal, stopword filtering, lemmatization) with `03_preprocesamiento_con_lematizacion.py`  
   - Results saved to results/tables/

2. **Vectorization**  
   - TF–IDF  
   - Word2Vec (pretrained)  
   - SBERT (pretrained)  
   The script `03_vectorize.py` outputs matrices to results/vectorizers/

## 🚀 Installation

- Clone the repository with `git clone https://github.com/YOURUSER/TextMineML.git` and change into the TextMineML directory  
- Create the environment with `mamba env create -f environment.yml` then `mamba activate prograv`, or install dependencies via `pip install -r requirements.txt`  
- (Optional) Install external tools via `conda install -c bioconda mafft clustalo fasttree iqtree`

## 📁 Project Structure

TextMineML/  
├── models/       Pretrained embeddings and models  
├── results/      Cleaned tables, vectors, clusters  
├── scripts/      Pipeline scripts  
├── figures/      Generated plots and visualizations  
├── README.md     Project overview and instructions  

## 🧠 Pretrained Models

- **Word2Vec**: `wiki-news-300d-1M-subword.vec` (download from FastText, unzip into `models/`)  
- **SBERT**: `all-mpnet-base-v2` (clone from Hugging Face into `models/` with Git LFS)

## 🚩 Usage Overview

Run the preprocessing, vectorization, clustering, and visualization scripts in sequence. Outputs appear in `results/` and `figures/`.

## 📊 Example Output

![UMAP projection](figures/basic/umap.png)  
*UMAP projection of document embeddings*

![Silhouette Scores Comparison](figures/basic/silueta_score_comparison.png)  
*Silhouette score comparison across different cluster counts*

![Top Words in All Clusters](figures/basic/top_palabras_all_clusters.png)  
*Most frequent words per cluster*

![Article Count per Cluster](figures/basic/barras_articulos_cluster.png)  
*Number of articles in each cluster*

![Word Cloud for Cluster 1](figures/basic/wordcloud.png)  
*Word cloud visualization for cluster 1*

## ❗ Troubleshooting

- Ensure pretrained model files exist in `models/`  
- Increase system memory or swap for large corpora  
- Recreate the environment to fix dependency issues

