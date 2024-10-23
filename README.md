# Single Cell Clustering Analysis Using Seurat

*Author: Luis Fernando Nagano*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![R Version](https://img.shields.io/badge/R-%3E%3D%204.0-blue)](https://cran.r-project.org/)

---

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Dataset](#dataset)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Analysis Workflow](#analysis-workflow)
- [Results](#results)
- [Visualizations](#visualizations)
- [Reproducibility](#reproducibility)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)

---

## Introduction

This repository contains a comprehensive pipeline for single-cell RNA sequencing (scRNA-seq) data analysis using the **Seurat** package. The workflow covers all the key steps from data preprocessing to cell type identification, showcasing best practices in computational biology.

The project is ideal for scRNA-seq analysis and is suitable for presentation to industry leaders in biotechnology and data science.

## Features

- **Automated Data Download and Preprocessing**
- **Stringent Quality Control Procedures**
- **Identification of Highly Variable Genes**
- **Advanced Dimensionality Reduction Techniques**
- **Clustering Algorithms for Single-Cell Data**
- **Marker Gene Expression Analysis**
- **Publication-Ready Data Visualizations**
- **Reproducible Analysis Workflow**

## Dataset

The analysis uses the **PBMC 3k** dataset from 10x Genomics, a widely-used benchmark in the field. The dataset consists of 3,000 peripheral blood mononuclear cells from a healthy donor.

- **Source**: [10x Genomics](https://support.10xgenomics.com/single-cell-gene-expression/datasets/1.1.0/pbmc3k)
- **Data Type**: Single-cell 3' RNA-seq

## Prerequisites

- **Operating System**: Windows, macOS, or Linux
- **R (version >= 4.0)**
- **RStudio (optional but recommended)**

### Required R Packages

- `Seurat` (version >= 4.0)
- `dplyr`
- `ggplot2`
- `patchwork`

Install the required packages using:

```R
install.packages(c("Seurat", "dplyr", "ggplot2", "patchwork"))
```

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/SingleCell_Seurat_Analysis.git
   cd SingleCell_Seurat_Analysis
   ```

2. **Install Dependencies**

   Open R or RStudio and install the required packages if not already installed.

## Usage

### Running the Analysis

1. **Open the R Markdown File**

   Open `SingleCell_Seurat_Analysis.Rmd` in RStudio.

2. **Execute the Script**

   Knit the R Markdown file to generate the HTML report:

   - Click on `Knit` in RStudio.
   - Or run:

     ```R
     rmarkdown::render("SingleCell_Seurat_Analysis.Rmd")
     ```

### Output

- **HTML Report**: A comprehensive report detailing each step of the analysis.
- **Plots**: High-resolution plots saved in the `output` directory.
- **Seurat Object**: The final Seurat object saved as `pbmc3k_final.rds` in the `output` directory.

## Analysis Workflow

The workflow is structured as follows:

1. **Data Acquisition**

   - Automated download of the PBMC dataset.
   - Loading the data into R using `Read10X`.

2. **Quality Control and Filtering**

   - Calculation of mitochondrial gene percentages.
   - Visualization of QC metrics.
   - Filtering cells based on feature counts and mitochondrial content.

3. **Normalization and Scaling**

   - Normalization using `NormalizeData`.
   - Identification of highly variable features with `FindVariableFeatures`.
   - Scaling the data using `ScaleData`.

4. **Dimensionality Reduction**

   - Principal Component Analysis (PCA) with `RunPCA`.
   - Determination of significant PCs using `ElbowPlot` and `DimPlot`.

5. **Clustering**

   - Construction of a K-nearest neighbors (KNN) graph with `FindNeighbors`.
   - Clustering cells using `FindClusters`.

6. **Visualization**

   - UMAP for non-linear dimensional reduction via `RunUMAP`.
   - Visualization of clusters and marker genes.

7. **Marker Gene Identification**

   - Identification of cluster markers using `FindAllMarkers`.
   - Visualization of marker expression across clusters.

8. **Cell Type Annotation**

   - Assigning biological identities to clusters based on marker genes.
   - Visualization of annotated clusters.

## Results

The analysis successfully identifies major immune cell types within the PBMC dataset, including:

- **T cells**: Naive CD4+, Memory CD4+, CD8+ T cells
- **B cells**
- **Natural Killer (NK) cells**
- **Monocytes**: CD14+ and FCGR3A+ subsets
- **Dendritic cells**
- **Platelets**

Marker genes such as *MS4A1*, *CD79A* (B cells), *CD3E* (T cells), *GNLY*, and *NKG7* (NK cells) are identified and used for cell type annotation.

## Visualizations

Key visualizations generated during the analysis include:

- **QC Violin Plots**: Assessing cell quality metrics such as mitochondrial content and gene count.
  ![QC Violin Plot](path/to/qc_violin_plot.png)
- **Variable Feature Plot**: Highlighting highly variable genes in the dataset.
  ![Variable Feature Plot](path/to/variable_features.png)
- **PCA and Elbow Plots**: Evaluating the dimensionality reduction process.
  ![Elbow Plot](path/to/elbow_plot.png)
- **PCA Scatter Plot**: Visualizing key principal components.
  ![PCA Scatter Plot](path/to/pca_scatter.png)
- **UMAP Plot**: Visualizing clusters in reduced dimensions using UMAP.
  ![UMAP Plot](path/to/umap_plot.png)
- **Labeled UMAP Plot**: Annotating the UMAP plot with identified cell types.
  ![Labeled UMAP Plot](path/to/umap_labeled.png)
- **Violin Plots of Marker Genes**: Displaying expression levels of key marker genes across different clusters.
  ![Violin Plot](path/to/violin_plot_markers.png)

All plots are saved in the `output` directory and are publication-ready.

## Reproducibility

To ensure reproducibility:

- **Session Information**: Included at the end of the analysis to record R version and package versions.
- **Seed Setting**: If random processes are used, seeds are set for reproducibility.
- **Dependencies**: All package versions are specified.

## Contributing

Contributions are welcome. To contribute:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/YourFeature`.
3. Commit your changes: `git commit -am 'Add your feature'`.
4. Push to the branch: `git push origin feature/YourFeature`.
5. Open a pull request.

Please ensure that your contributions adhere to the project's coding standards and include appropriate documentation.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- **10x Genomics**: For providing the PBMC dataset used in this analysis.
- **Seurat Development Team**: For creating and maintaining the Seurat package.
- **Open-Source Community**: For contributing to the development of bioinformatics tools and resources.

## Contact

For any questions, feedback, or collaboration opportunities, please contact:

**Luis Fernando Nagano**

- **Email**: nagano.luis@gmail.com
- **LinkedIn**: [Luis Fernando Nagano](www.linkedin.com/in/luis-fernando-nagano-7585b82a8)
- **GitHub**: [luisfernando](https://github.com/LuisNagano)
