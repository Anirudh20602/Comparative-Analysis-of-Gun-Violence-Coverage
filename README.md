# Comparative Analysis of Gun Violence Coverage

This project analyzes how different news outlets (CNN, Fox, NYT, WSJ) portray victims and shooters in gun violence incidents using NLP techniques including coreference resolution, description extraction, semantic clustering, and statistical analysis.

## Project Overview

**Tasks Implemented:**
1. Context Extraction with Coreference Resolution (FastCoref)
2. Description Extraction (Dependency Parsing + POS-based Window)
3. Description Clustering (SentenceTransformer + Agglomerative Clustering)
4. Manual Cluster Evaluation
5. Cross-Outlet Frequency Analysis
6. Statistical Hypothesis Testing (Chi-Squared)

## Setup & Execution

### Prerequisites
```bash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
```

### Running on Google Colab
1. Upload `HW5_FINAL.ipynb` to Google Colab
2. Ensure your dataset (`data_100.zip`) is in: `My Drive/Colab Notebooks/NLP HW5/`
3. Run all cells sequentially
4. The notebook will automatically:
   - Mount Google Drive
   - Unzip the dataset
   - Process all articles
   - Generate visualizations
   - Save results to CSV

### Running Locally
1. Place dataset in `data/raw/` directory
2. Open and run `HW5_FINAL.ipynb` in Jupyter
3. Results will be saved in the notebook directory

## Output Files

The notebook generates:
- `processed_articles_resolved.csv` - Articles with resolved coreferences
- `labeled_clusters.csv` - Extracted descriptions with cluster assignments
- Frequency heatmaps and statistical test results (displayed in notebook)

## Project Structure

```
HW5/
├── notebooks/
│   └── HW5_FINAL.ipynb      # Main analysis notebook (all code consolidated)
├── data/
│   └── raw/                 # Raw article files (100 articles)
├── Homework 5.pdf           # Assignment instructions
├── README.md                # This file
├── requirements.txt         # Python dependencies
├── labeled_clusters.csv     # Output: Extracted descriptions with cluster assignments
└── processed_articles_resolved.csv  # Output: Articles with resolved coreferences
```

## Key Features

- **Coreference Resolution**: Uses FastCoref neural model with security patch for compatibility
- **Robust Extraction**: Combines dependency parsing with proximity-based POS extraction
- **Semantic Clustering**: Agglomerative clustering on sentence embeddings (distance_threshold=0.8)
- **Statistical Rigor**: Chi-squared tests for cross-outlet comparison

## Notes

- The notebook includes a monkeypatch for FastCoref model loading to bypass security restrictions in newer transformers versions
- All analysis is self-contained in a single notebook for easy execution and submission
