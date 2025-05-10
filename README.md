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
