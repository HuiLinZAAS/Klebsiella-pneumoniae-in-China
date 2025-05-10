# Klebsiella-pneumoniae-in-China
Global and local genomics reveal an unexpectedly higher antimicrobial resistance burden in nonhuman than human Klebsiella pneumoniae in China

Overview
This project provides a Python script that performs resampling (bootstrap) analysis on antimicrobial resistance (AMR) data from various databases. It evaluates the differences in AMR metrics between databases and performs multiple statistical tests to determine if the differences are significant. The script generates summary statistics and visualizations to help in understanding and comparing the AMR data across databases.

Key Steps:
Load and preprocess data from multiple Excel worksheets.

Perform bootstrap resampling to calculate the mean of four key AMR metrics: AMR score, AMR class, AMR gene, and VF score.

Conduct statistical tests (ANOVA, Kruskal-Wallis, Tukey HSD, Dunn's test) to assess the significance of differences.

Generate visualizations (box plots) comparing these metrics across different databases.

Save results to CSV files and save box plots as images.
Requirements
Before running the script, ensure that you have the following Python libraries installed:

pandas

numpy

scipy

scikit-posthocs

statsmodels

matplotlib

seaborn

You can install these libraries using pip:

bash
复制
编辑
pip install pandas numpy scipy scikit-posthocs statsmodels matplotlib seaborn
Files
1. Main Script (bootstrap_analysis.py)
This script performs the analysis as described above. It includes functions for resampling, statistical testing, and visualization.

2. Input Data Files
Excel File (human for resampling.xlsx): This file should contain multiple sheets, each corresponding to a different database, with the following columns:

AMRscore: Antimicrobial Resistance score.

AMRclass: Class of Antimicrobial Resistance.

AMRgene: Antimicrobial Resistance gene.

VFscore: Virulence Factor score.

Sample List Files (Community_sample_list.xlsx, Hospital_sample_list.xlsx): These files contain lists of strains sampled from community and hospital environments. These samples will be used to create bootstrap resamples.

3. Output Files
CSV Files: The resampling results for each sample size and database are saved as CSV files with the following format: non_human_bootstrap_means_{size}_samples.csv.

Box Plot Images: A series of box plot images for each metric (AMRscore, AMRclass, AMRgene, VFscore) comparing the different databases, saved in .png format.

Usage
Prepare the Data Files:

Ensure that the Excel file human for resampling.xlsx is properly formatted with multiple sheets, each containing the necessary columns for AMR data.

Prepare the sample list files Community_sample_list.xlsx and Hospital_sample_list.xlsx.

Run the Script:

Set the file paths for your input files and output directory in the script.

Define the sample sizes and number of bootstrap iterations in the script. These are adjustable as needed (e.g., [500, 1000, 1500] for sample sizes and 1000 for iterations).

bash
复制
编辑
python bootstrap_analysis.py
Interpret the Results:

The script will output summary statistics (mean, median, max, min) for each metric and sample size in CSV files.

Statistical significance tests (ANOVA, Kruskal-Wallis, Tukey HSD, and Dunn’s test) will be performed, and the results will be printed in the console.

Box plots for each metric will be generated and saved in the specified output directory.

Statistical Analysis
The script performs the following statistical tests to assess whether the differences in AMR metrics between databases are significant:

ANOVA (Analysis of Variance): Compares the means of the AMR metrics across databases. It checks if there are any statistically significant differences between the means.

Kruskal-Wallis Test: A non-parametric test that compares the ranks of the AMR metrics across databases, useful when the data is not normally distributed.

Tukey HSD (Honestly Significant Difference): A post-hoc test that identifies which specific groups (databases) differ after ANOVA.

Dunn’s Test: A post-hoc test used after Kruskal-Wallis to compare all possible pairs of groups and identify which ones are significantly different.

Visualization
The script generates box plots for each metric (AMRscore, AMRclass, AMRgene, VFscore) comparing different databases. These plots are saved in .png format in the specified output directory. The plots are designed with large fonts for better readability.

Box Plot Details:
X-axis: Databases (from the Excel sheet).

Y-axis: AMR metric values (e.g., AMRscore, AMRclass).

Hue: Different databases will be distinguished using different colors in the plot.

Example Output
CSV Files:
non_human_bootstrap_means_500_samples.csv: Contains bootstrap mean values for 500 sample size.

non_human_bootstrap_means_1000_samples.csv: Contains bootstrap mean values for 1000 sample size.

Console Output:
For each metric and sample size, the following will be printed:

arduino
复制
编辑
AMRscore ANOVA results (Sample size 500): F-statistic = 3.12, p-value = 0.045 -> Significant
AMRscore Kruskal-Wallis results (Sample size 500): H-statistic = 2.89, p-value = 0.048 -> Significant
Box Plot Image:
A box plot image comparing AMRscore across different databases at the specified sample size.

Conclusion
This analysis allows researchers to compare the distribution of AMR metrics between databases using robust statistical tests and resampling methods. The results, including statistical tests and visualizations, help to understand the variability and significance of AMR data across different sources.

