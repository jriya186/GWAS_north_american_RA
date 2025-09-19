# GWAS Analysis of Rheumatoid Arthritis (NARAC Dataset)

This project was my final course project, where I explored the North American Rheumatoid Arthritis Consortium (NARAC) GWAS dataset to investigate genetic associations with rheumatoid arthritis (RA). The goal was to perform quality control, sex-stratified genome-wide association studies, and polygenic risk score (PRS) analysis, highlighting both methodology and findings.

## Dataset
Individuals: 2,062 (868 RA cases, 1,194 controls)
Variants: ~544,000 SNPs before QC
Publicly available GWAS dataset curated by NARAC.

### Methods & Tools
QC & GWAS: PLINK
Population Structure: EIGENSOFT (PCA analysis)
Meta-analysis: METAL
Polygenic Risk Scores: PRSice
Visualization & Scripting: R, Bash
Key processing steps:
SNP & individual filtering by MAF, missingness, and Hardy–Weinberg equilibrium.
LD pruning and PCA to control for ancestry/population structure.
Logistic regression GWAS with sex-stratified analysis (male vs. female).
Meta-analysis across sexes to identify shared loci.
Polygenic risk score (PRS) construction using external RA GWAS summary statistics.

### Key Findings
1. QC Results: After filtering, 104,505 high-quality independent SNPs remained.
2. PCA: PC1, PC2, and PC4 significantly correlated with case-control status → used as covariates.
3. Sex-stratified GWAS:
3a. Females: Several SNPs on chromosome 6 surpassed genome-wide significance (p < 5 × 10⁻⁸).
3b. Males: No genome-wide significant hits (likely underpowered).
* Interesting note: SNPs rs532098 and rs405875 showed opposite effect directions between sexes.
4. Meta-analysis: Reinforced strong chromosome 6 signals, concordant with RA immune-related loci.
5. PRS Analysis: PRS explained unusually high variance (~91.8%), suggesting possible dataset overlap or methodological inflation.

## Limitations
Smaller male subset reduced statistical power.
Potential population stratification artifacts, despite PCA correction.
Fixed-effects meta-analysis may underestimate heterogeneity.
High PRS variance explained likely reflects technical issues (overlap, p-value thresholding).


