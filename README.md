# Gene Expression Signature for Chemoresistance in Cancer

# Overview
The development of drug resistance remains a critical challenge in cancer therapy, often leading to treatment failure and poor patient outcomes. This project addresses this challenge by integrating five distinct Gene Expression Omnibus (GEO) datasets to identify a robust biomarker signature for chemoresistance. By leveraging both bioinformatics and machine learning, this study identifies a 50-gene signature capable of predicting drug-resistant phenotypes with high accuracy

# Objectives
Perform Differential Expression Analysis (DEA) on multiple cancer drug resistance datasets.
Develop and validate a Random Forest machine learning model for classifying cell sensitivity.
Identify a minimal, high-impact set of predictive gene biomarkers.
Conduct functional enrichment and network analysis to elucidate the biological roles of identified markers.

# Datasets

The study utilized five publicly available datasets from the NCBI GEO database, all generated using the Affymetrix Human Genome U133 Plus 2.0 Array (GPL570) platform to ensure technical compatibility:
|  GEO ID      ||                    Study Title                            |
|--------------||-----------------------------------------------------------|
| GSE11440     ||  Methotrexate resistance in HT29 colon cancer cells       |
| GSE27473     ||  MCF7 cell line after silencing of Estrogen receptor      |
| GSE69657     ||  HOXB8 and KLK11 expression for FOLFOX4 chemotherapy      |
| GSE15709     ||  A2780 (cisplatin-sensitive) and Round5 A2780 (resistant) |
| GSE26459     ||  High-throughput screen for tamoxifen resistance          | 

# Methodology
Data Preprocessing: Cleaning and formatting of series matrix files using Python (pandas, os).
Differential Expression Analysis (DEA): Identifying genes significantly dysregulated between 'sensitive' and 'resistant' samples.
Master Gene Signature: Pooling the most significant genes from each dataset to create a non-redundant list of 298 unique genes.
Machine Learning: Training a Random Forest classifier to identify the most predictive features.
Downstream Bioinformatic Analysis: * PPI Network: Constructed via the STRING database.
Hub Gene Identification: Using the CytoHubba plugin in Cytoscape.
Functional Enrichment: GO (Biological Process, Cellular Component, Molecular Function), KEGG, Reactome, and GWAS Catalog

# Key Results
High Performance: The Random Forest model achieved an Area Under the Curve (AUC) of 0.9219, demonstrating excellent discriminatory power.
50-Gene Signature: Identified a refined panel of 50 genes most predictive of chemoresistance.
Hub Genes: Four central hub genes were identified as critical regulators: H2BC12, JUN, S100A10, H2BS1.
Biological Insights: Functional analysis linked these genes to pathways such as NOTCH signaling, programmed cell death, and transcription regulation

# Repository Structure
├── data/               # Metadata and processed series matrix files
├── scripts/            # Python scripts for DEA and Machine Learning
├── results/            # Volcano plots, ROC curves, and Confusion Matrices
├── network_analysis/   # Cytoscape and STRING network visualizations
└── README.md           # Project documentation

# Conclusion
This study successfully identified a high-performing 50-gene biomarker signature and four key hub genes centrally positioned in cancer-relevant pathways. These findings hold significant potential for developing diagnostic tools to guide personalized cancer therapy and overcome drug resistance.
