# Identification-of-protein-biomarkers-for-kidney-carcinoma-project-2026
This Thesis explores a proteomic based strategy to distinguish between two major sub-
types of kidney cancer: Kidney Renal Clear Cell Carcinoma (KIRC) and Kidney Renal
Papillary Cell Carcinoma (KIRP). A key challenge in Renal Cell Carcinoma (RCC)
is that it often develops without noticeable symptoms in the early stages, leading to
treatment options becoming more limited and outcomes are less favorable. With this
in mind, there’s an urgent need to uncover molecular mechanisms driving RCC to en-
able earlier detection and improved patient outcomes. While genetic-level studies have
advanced our understanding, there is a growing interest in protein level investigations
for identifying more accurate and reliable biomarkers.

To address this gap, this study utilizes protein abundant data from The Cancer
Proteome Atlas (TCPA) to identify potential biomarkers that can distinguish be-
tween KIRC and KIRP. The analysis involved rigorous quality control, exploratory
data analysis, differential protein abundant analysis using the Limma package, path-
way enrichment through KEGG and Gene Ontology (GO), and supervised machine
learning. Notably, Principal Component Analysis (PCA) revealed a clear molecular
separation between the subtypes, and 46 differentially abundant proteins (DAPs) were
identified, including 25 upregulated and 21 downregulated. GO and KEGG pathway
analyses revealed that the DEPs upregulated in KIRC were primarily associated with
Focal adhesion and EGFR signaling pathways, whereas those upregulated in KIRP
were mainly involved in p53 signaling and DNA repair processes.

To evaluate how well these proteins could classify the cancer subtypes, three ma-
chine learning models ElasticNet, Naive Bayes, and XGBoost were trained and tested
using standard performance metrics, including accuracy, precision, recall, F1-score,
and AUC-ROC. All models demonstrated excellent performance, achieving 98.5% ac-
curacy and high F1-scores. ElasticNet and Naive Bayes models showed strong pre-
cision, while XGBoost stood out with perfect recall and the highest AUC (0.987),

making it especially effective at minimizing false negatives, an essential feature for clin-
ical applications. Across all models, feature importance analysis consistently identified
PEA15 pS116, CLAUDIN7 , and YAP pS127 as top ranked biomarker candidates.
These findings not only reinforce the value of proteomics in cancer classification but
also highlight the promise of machine learning in advancing subtype specific diagnostics
for kidney cancer.

Description of Dataset:
A total of 653 samples were downloaded for this study; 445 of them were KIRc samples,
and the remaining 208 KIRP samples. Each sample have 234 Proteins.

Dev-Enviroment:
1) R Project
R Project is a programming language and software environment. It is widely used in
bioinformatics, data science, and research for tasks like data manipulation, statistical
modeling, and creating high-quality plots. R has a large community and many packages
(via CRAN and Bioconductor) that extend its functionality, making it a powerful tool
for analyzing and interpreting complex datasets. The Study was done using R because
its designed for statistical computing, data analysis, and visualization which is what
we need.

2) Bioconductor
Bioconductor is an open-source project that provides a collection of R packages specif-
ically designed for the analysis of genomic and biological data. It supports tasks like
RNA-seq analysis, microarray processing, and genome annotation. Built on the R lan-
guage, Bioconductor is widely used in bioinformatics and offers tools that are reliable,
well-documented, and regularly updated for reproducible research. Limma, impute,
cluster and visulaization Packages played key roles in the analysis and were utilized.

3) Limma Package
Limma (Linear Models for Microarray Data) is a widely used statistical tool designed
for analyzing gene or protein expression data from high-throughput experiments. It
uses linear models to compare expression levels between groups and applies statistical
methods to improve the reliability of the results, even with smaller sample sizes. This
approach increases the statistical power to detect true differences in expression. In this
study, Limma was applied to identify differentially abundant proteins between kidney
cancer subtypes. resulting in a list of proteins that were significantly upregulated or
downregulated.

4) David Package
To understand the biological meaning behind the differentially abundant proteins, we
used a tool called DAVID (Database for Annotation, Visualization, and Integrated
Discovery). DAVID helps find patterns and functions related to a group of genes or
proteins. We uploaded the list of differentially abundant proteins into DAVID, and it
matched them with known biological pathways and functions. From this, we were able
to extract Gene Ontology (GO) terms, which describe the roles of proteins in biologi-
cal processes, molecular functions, and cellular components. We also identified KEGG
pathways, which show groups of proteins working together in important biological path-
ways. This helped us better understand how these proteins might be involved in kidney
cancer development.

6) Machine learning models
Machine learning
Machine learning (ML) is a branch of artificial intelligence that enables computers to
learn patterns from data and make decisions or predictions without being explicitly
programmed. In biomedical research, ML has emerged as a powerful tool for analyzing
large-scale datasets such as protein expression profiles. These algorithms can identify
hidden patterns and classify complex biological states, such as distinguishing between

cancer subtypes or identifying potential biomarkers for diagnosis and treatment. ML
approaches are particularly valuable in precision medicine, where the goal is to tailor
healthcare decisions based on individual molecular profiles.

In this study, three machine learning models were employed to classify kidney cancer
subtypes (KIRC vs. KIRP) based on differentially abundant proteins. First, Naive
Bayes is a simple probabilistic classifier based on Bayes’ theorem, assuming indepen-
dence among features; despite its simplicity, it can perform surprisingly well in high-
dimensional biological data. Second, XGBoost (Extreme Gradient Boosting) is a power-
ful ensemble learning method that builds multiple decision trees sequentially, optimizing
performance using gradient boosting; it is known for its speed, accuracy, and ability
to handle complex interactions between features. Third, Elastic Net is a regularized
regression model that linearly combines the techniques of Lasso (L1) and Ridge (L2)
regression, making it suitable for datasets with correlated predictors and more features
than samples, as commonly seen in omics data. These models were selected for their
complementary strengths in handling the characteristics of proteomic datasets
