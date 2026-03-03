# Cybersecurity Behavioral Clustering

## Project Overview
This project is part of my Unsupervised Learning course and applies 
clustering techniques to a cybersecurity behavioral dataset. The goal 
is to discover hidden behavioral patterns among 10,000 individuals 
based on their digital and physical activity — without relying on 
labeled data.

## Problem Statement
Traditional threat detection relies on binary labels (suspicious vs. 
not suspicious). This project explores whether unsupervised clustering 
can reveal richer behavioral archetypes that go beyond simple 
classification — helping security teams prioritize investigations more 
effectively.

## Dataset
- File: suspicious_behavior_dataset_extended.csv
- Records: 10,000
- Features: 14 behavioral attributes
- Key features include: encrypted app usage, GPS zone visits, 
  VPN usage, military zone proximity, night movements, and more.

## Models Applied
| Model | Silhouette Score | Result |
|---|---|---|
| KMeans k=3 | 0.0584 | Under-segments |
| KMeans k=4 | 0.0610 | ✅ Recommended |
| KMeans k=5 | 0.0588 | Over-segments |
| Agglomerative k=4 | 0.0601 | Valid alternative |
| DBSCAN | N/A | Not suitable |

## Key Findings
- **Cluster 0** – Low-Risk Passive: 100% VPN users, 29.4% suspicious rate
- **Cluster 1** – High-Risk Operatives: 41.5% suspicious rate, 
  4.6 hrs/day encrypted app usage
- **Cluster 2** – Mid-Risk Digital: Low GPS, minimal footprint, 
  6.9% suspicious rate
- **Cluster 3** – Surveillance Suspects: GPS visits 3x average, 
  no VPN or encryption, 6.6% suspicious rate

## Tools & Libraries
- Python 3
- scikit-learn
- Pandas & NumPy
- Matplotlib & Seaborn
- Jupyter Notebook

## Files in this Repository
- `cybersecurity_unsupervised_learning.ipynb` — Full Python notebook
- `Cybersecurity_Unsupervised_Learning_Report.pdf` — Project report
- `Cybersecurity_Unsupervised_Learning_Report.docx` — Word version
- `suspicious_behavior_dataset_extended.csv` — Dataset
- `README.md` — This file

## How to Run
1. Clone this repository
2. Install required libraries:
   pip install pandas numpy scikit-learn matplotlib seaborn
3. Open the notebook:
   jupyter notebook cybersecurity_unsupervised_learning.ipynb
4. Run all cells from top to bottom

## Next Steps
- Add temporal features from activity timestamps
- Build graph-based clustering using contact network data
- Train cluster-specific supervised models
- Deploy KMeans centroids as a real-time scoring API

## Author
Built as part of the Unsupervised Learning Course Project.
Connects to previous work in credit card fraud detection.
