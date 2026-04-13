# Breast-Cancer-Bioinformatics-Analysis

This repository presents a complete bioinformatics workflow to identify key genes, regulatory mechanisms, and potential therapeutic targets in breast cancer using publicly available gene expression datasets.

## Overview

Breast cancer progression is driven by complex molecular mechanisms. This project integrates multiple datasets and analytical tools to:

1. Identify differentially expressed genes (DEGs)
2. Extract common genes across datasets
3. Construct protein–protein interaction (PPI) networks
4. Detect hub genes and functional modules
5. Analyze transcription factors (TFs) and miRNAs
6. Identify potential drugs targeting key genes

## Workflow Pipeline

1. GEO Datasets
2. DEG Analysis (GEO2R)
3. Common Genes (Venn Diagram)
4. PPI Network (STRING)
5. Hub Genes (Cytoscape - cytoHubba)
6. Module Detection (MCODE)
7. Regulatory Network (TF + miRNA)
8. Drug Enrichment (Enrichr)

## Dataset Used

Dataset          Description

1. GSE42568 -    Gene expression profiling of 104 breast cancer and 17 normal breast biopsies.
2. GSE65194 -    Gene expression profiling of 130 breast cancer samples (41 TNBC ; 30 Her2 ; 30 Luminal B and 29 Luminal A),                   11 normal breast tissue samples and 14 TNBC cell lines.
3. GSE70947 -    Gene expression profiling of 296 total samples: 148 breast adenocarcinoma, 148 paired adjacent normal                         breast tissue

All datasets were obtained from NCBI GEO (https://www.ncbi.nlm.nih.gov/geo/).

## Tools \& Resources

1. STRING - PPI network construction (https://string-db.org)
2. Cytoscape - Network visualization (https://cytoscape.org/)
3. cytoHubba - Hub gene identification (https://apps.cytoscape.org/apps/cytohubba)
4. MCODE - Module detection (https://apps.cytoscape.org/apps/mcode)
5. NetworkAnalyst - TF and miRNA networks (https://www.networkanalyst.ca/)
6. Enrichr - Drug enrichment analysis (https://maayanlab.cloud/Enrichr/)

## Methodology

### 1\. DEG Identification

Tool used: GEO2R (https://www.ncbi.nlm.nih.gov/geo/geo2r/);
Genes were considered differentially expressed based on:



\- Adjusted p-value < 0.05

\- |logFC| > 1


These criteria ensure both statistical significance and biological relevance.


\[I] GSE42568: Total DEGs - 6417; Upregulated - 3063; Downregulated - 3354

\[II] GSE65194: Total DEGs - 7785; Upregulated - 2573; Downregulated - 5212

\[III] GSE70947: Total DEGs - 646; Upregulated - 321; Downregulated - 325

### 2\. Common Gene Identification

Method: Venn diagram;
Tool used: Venny 2.1.0 (https://bioinfogp.cnb.csic.es/tools/venny/);
Result: 124 common DEGs found

<img width="1280" height="1280" alt="Venn Results" src="https://github.com/user-attachments/assets/e72c77a9-dc96-4300-aeda-4f0942273137" />


### 3\. PPI Network Construction

Tool used: STRING;

Network stats:
\[I] number of nodes - 122
\[II] number of edges - 145
\[III] average node degree - 2.38
\[IV] PPI enrichment p-value - 8.51e-07


<img width="5013" height="5153" alt="String Network" src="https://github.com/user-attachments/assets/a94dea76-b077-41c4-84c5-1f132774819e" />


### 4\. Hub Gene Identification

Tool used: Cytoscape (cytoHubba);
Method: Degree centrality

Tol 10 Hub genes: EZH2, CCNB1, RAD51, BUB1B, NUF2, UHRF1, KIF2C, HDAC1, ASPM, ESPL1

### 5\. Module Detection

Tool used: Cytoscape (MCODE);

top MCODE cluster (functional module):
Score - 10.6;
Nodes - 11;
Edges - 53 (highly interconnected)

Genes: NUF2, EZH2, HMMR, ESPL1, SKA3, UHRF1, CCNB1, BUB1B, RAD51, ASPM, KIF2C

### 6\. Final Key Genes

Genes were finalized from the intersection of Hub genes (cytoHubba) and top MCODE cluster: EZH2, CCNB1, RAD51, BUB1B, NUF2, UHRF1, KIF2C, ASPM, ESPL1

### 7\. Regulatory Network Analysis

Tool used: NetworkAnalyst

1. Transcription Factors (TFs):
ELF1, KDM5A, KLF9, KLF1, POLR2A, IRF1, ZNF175, ZNF263

<img width="8721" height="7897" alt="TF Gene Interactions" src="https://github.com/user-attachments/assets/13b0f7c7-62c3-49e4-b663-762258e7cdb8" />


3. miRNAs:
hsa-miR-193b-3p, hsa-let-7a-5p, hsa-let-7b-5p, hsa-miR-192-5p, hsa-miR-215-5p, hsa-miR-124-3p, hsa-miR-25-3p, hsa-miR-92a-3p

<img width="8721" height="7897" alt="miRNA TF Gene Interactions" src="https://github.com/user-attachments/assets/676797c8-268c-47a6-895d-863fa11790f9" />




### 8\. Drug Enrichment Analysis

Tool used: Enrichr (DSigDB(Drug SIGnatures DataBase))

Top candidate drugs: LUCANTHONE, Phytoestrogens, Troglitazone, Etoposide, Enterolactone, Calcitriol, Resveratrol

<img width="708" height="299" alt="DSigDB Drug" src="https://github.com/user-attachments/assets/39d076cb-2c8b-4700-a29b-1e4236e07d54" />


## Key Findings

Core genes are mainly involved in:

1. Cell cycle regulation
2. DNA repair
3. Epigenetic modification

Regulatory network reveals: Multi-layer gene control (TF + miRNA)

Drug enrichment suggests: Potential therapeutic candidates targeting key pathways

## Results Summary

|Step|Output|
|-|-|
|DEGs|16605|
|Common Genes|124|
|Hub Genes|10|
|Final Key Genes|9|
|TFs Identified|8|
|miRNAs Identified|8|

## Future Work

1. Experimental validation (qPCR, Western blot)
2. Survival analysis
3. Molecular docking and MD simulations
4. Clinical validation

## 👨‍🔬 Author

Aman Jha

MSc Bioinformatics

## If you find this useful

Give this repository a ⭐ and feel free to fork!

