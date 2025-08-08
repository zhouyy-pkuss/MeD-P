# MeD-P: A Framework for Biomaterial-Induced Mesenchymal Stem Cell Differentiation Prediction
MeD-P (Mesenchymal stem cell Differentiation Prediction) is a computational framework designed for predicting the lineage fate of human mesenchymal stem cells (hMSCs) induced by biomaterials. By integrating large-scale public RNA-seq data, MeD-P enables accurate and early classification of hMSC differentiation into three key lineages: osteogenesis, chondrogenesis, and adipogenesis.

---

## 📚 Citation
If you use MeD-P in your research, please cite the following paper:

> "Assessing Biomaterial-Induced Stem Cell Lineage Fate by Machine Learning-Based Artificial Intelligence"
> [Yingying Zhou, Xianfeng Ping, Yusi Guo, Boon Chin Heng, Yijun Wang, Yanze Meng, Shengjie Jiang, Yan Wei, Binbin Lai*,Xuehui Zhang*,Xuliang Deng*]  
> *Advanced Materials*, 2023, 35:2210637  
> DOI: [10.1002/adma.202210637](https://doi.org/10.1002/adma.202210637)

---

## 🎯 Overview
MeD-P integrates a comprehensive cell-type-specific gene expression reference profile constructed from publicly available RNA-seq datasets related to tri-lineage differentiation of hMSCs. Using a k-nearest neighbors (kNN)-based classification model, MeD-P predicts the differentiation trajectory of hMSCs exposed to various biomaterials with high accuracy.

Key features:
- Predicts osteogenic, chondrogenic, and adipogenic differentiation fates.
- Achieves an overall accuracy of 90.63% on independent test datasets.
- Outperforms traditional marker gene-based models (80.21% accuracy).
- Enables early prediction — as early as one week after hMSC seeding on biomaterials.
- Applicable across diverse biomaterial types, including polymers, ceramics, and composites.

---

## 🛠️ Requirements

MeD-P is implemented in R and requires the following:

- R version 4.1.1 or higher
- Required R packages:
  - `ComBat-seq`
  - `DaMiRseq`
  - `edgeR`
  - `ggplot2`
  - `reshape2`
  - `SummarizedExperiment`
  - `DESeq2`
  - `sva`
  - `RColorBrewer`
  - `tidyverse`

You can install the required packages using the following R code:

```r
install.packages(c("ComBat-seq","DaMiRseq","edgeR", "ggplot2", "reshape2", "SummarizedExperiment", "DESeq2", "sva", "RColorBrewer", "tidyverse"))
```
if you failed to install "ComBat-seq" and "DaMiRseq", you can load the files in example/code with the same functions.


📂 Repository Structure

After downloading MeD-P to your Downloads folder, the directory structure should look like this:

<pre>
~/Downloads/MeD-P/
├── MeD-P.Rmd               # Main script containing the full prediction pipeline
├── example/                # Folder with example data
│   ├── data/               # Example gene expression profile and metadata file
│   ├── model/              # Prediction model
│   ├── output/             # Example output predictions
│   └── code/               # Files including "ComBat-seq" and "DaMiRseq" functions
└── README.md               # This file
</pre>


🚀 How to Use MeD-P

You can follow the steps in "MeD-P.Rmd" file.

📎 Input Format

The input should be a CSV file with:
Rows: Genes (HGNC gene symbols)
Columns: Samples (first column should be gene as row names)
Values: raw count gene expression

See example/data/Testraw.csv for a complete example.

📤 Output

MeD-P generates the following in the specified output directory:

prediction_results.csv: Predicted lineage and classification confidence scores for each sample.
radar.png (optional): Visualization of predicted confidence scores.

🐛 Issues & Feedback

If you encounter any issues or have suggestions for improvement, please open an issue on GitHub.
You can also contact the first author by email: zhouyy@bjmu.edu.cn

📄 License

This project is licensed under the GNU Affero License - see the LICENSE file for details.
