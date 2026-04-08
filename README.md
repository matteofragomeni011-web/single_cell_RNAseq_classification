Single-Cell Transcriptomics Analysis with Pathway-Based Machine Learning

 Overview

This project analyzes single-cell RNA sequencing (scRNA-seq) data using pathway-level features derived from KEGG annotations. The goal is to classify cells based on their experimental conditions and to identify the biological processes driving these differences.

---

 Dataset
GEO accession: GSE165686
SOURCE: NCBI Gene expression Omnibus (GEO)

The dataset consists of single-cell gene expression profiles, where:

- Rows represent genes
- Columns represent cells

Gene expression values are processed and transformed into pathway-level features using KEGG functional annotations.

---

 Pipeline

1. Preprocessing

- Library size normalization
- Log transformation
- Quality checks and distribution analysis

2. Functional Annotation (KEGG)

- Download KEGG hierarchical file
- Parse pathway structure
- Map genes to pathways

3. Pathway Feature Construction

- Aggregate gene expression per pathway (mean)
- Build pathway-level feature matrix (cells × pathways)

4. Exploratory Analysis

- Distribution of pathway activity
- PCA visualization

5. Classification

- Model: Random Forest
- Train/test split (stratified)
- 5-fold cross-validation

6. Evaluation

- Accuracy
- Precision, Recall, F1-score (macro)
- Confusion matrix

7. Feature Importance

- Identification of key pathways driving classification
- Biological interpretation

8. Comparative Analysis

- Feature selection (top 20 pathways)
- Mean vs median aggregation comparison

---

 Results

Model| Accuracy| F1 (macro)
Mean (full)| 0.76| 0.73
Top 20 pathways| 0.74| 0.72
Median| 0.57| 0.45

Key Findings

- Pathway-based features effectively capture biological differences between conditions
- Protein synthesis and metabolic pathways are the most discriminative
- A small subset of pathways retains most of the predictive power
- Median aggregation performs poorly due to data sparsity

---

 Interpretation

The analysis reveals that differences between experimental conditions are primarily driven by pathways related to:

- Ribosome activity
- Protein synthesis and processing
- Cellular metabolism

These findings suggest that cellular growth and stress responses play a central role in distinguishing conditions.

---


 Technologies Used

- Python
- Scanpy
- NumPy / Pandas
- Scikit-learn
- Matplotlib / Seaborn

---

 Conclusions

This project demonstrates that pathway-level feature engineering combined with machine learning provides an effective and interpretable approach for analyzing single-cell transcriptomic data. The choice of aggregation method is critical, with mean-based features outperforming median-based ones in sparse datasets.

---

 Notes

- KEGG data were used for pathway annotation
- Large raw files are excluded from version control (.gitignore)

---

 Author

Project developed as part of a computational genomics assignment.
