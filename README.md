
# Identification of Biomarkers for ALS using RNA-Seq Data

## Introduction
This project aims to identify biomarkers for Amyotrophic Lateral Sclerosis (ALS) using RNA-Seq data from 174 samples coupled with their metadata. The process includes an initial quantitative analysis to understand the data, followed by coherent analysis techniques. Various methods are tested and tuned to improve prediction performance.

## Data Preprocessing
- **Data Distribution**: Analyzed the distribution of healthy vs. ALS samples and distribution across brain regions.
- **Observations**: Predominance of ALS class, and data uniformly distributed across brain regions.

## Grouped Analysis of Genes and Samples
### Gene Analysis
- **Variability**: Significant variation in the standard deviation of gene expression values.
- **Distribution**: Asymmetry between mean and median suggests non-uniform gene expression levels.

### Sample Analysis
- **Comparison**: Examined mean gene expression levels across samples.
- **Findings**: No significant signal found in mean, median, or standard deviation of gene expression levels.

## Principal Component Analysis (PCA)
- **Variance Explained**: Approximately 80 principal components needed to retain 90% of the information.
- **Visualization**: No clear separation of classes in initial principal components.
- Identified genes with the most significant impact on principal components.

## DESeq2 Analysis
In this project, DESeq2 was utilized for differential gene expression analysis.
The analysis produced p-values and adjusted p-values, which were then visualized using a volcano plot. 
This plot highlighted genes that were both statistically significant and exhibited substantial changes in expression.

## ElasticNet Regression
The goal of the ElasticNet regression was to identify key genes that distinguish ALS and other neurological diseases from healthy controls. 
- Cross-validation was employed to tune the parameters and avoid overfitting. 
- Performance metrics such as precision, F1 score, balanced accuracy, and Matthews correlation coefficient (MCC) were evaluated. 
- The analysis identified significant genes that contributed to the classification of samples, with the top influential genes listed based on their ElasticNet coefficients.

## XGBoost Analysis
Due to the non-linear separability of the data, XGBoost was selected as the optimal algorithm. The target variable was encoded, and the genes were integrated into the training of the XGBoost model. Hyperparameters, such as alpha, lambda, and gamma, were meticulously fine-tuned to improve the model's predictions.

## Conclusion
The findings from DESeq2, ElasticNet, and XGBoost analyses were integrated to create a comprehensive table of significant genes. 
This synthesis identified 100 candidate genes that consistently showed significance across all methods, highlighting their potential relevance as biomarkers for ALS.
