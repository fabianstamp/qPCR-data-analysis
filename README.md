# qPCR-data-analysis: Analysis of gene expresssion data from qPCR in R

## What is this script for?  

This is a simple R Markdown script for researchers interested in transitioning their qPCR analysis from GUI based platforms such as Prism or Excel to R. All files required to run the analysis with an example data set are provided.

## How to start?

You can run the analysis as is with the provided files. They include this script (**qPCRDataAnalysisNotebook.Rmd**) and an example data set (**qPCR_data.xlsx**).  If you want to run the analysis with your own experimental data, you will required the following information:  

* A list matching each tested sample with a condition (**condition**)
* Positional information of replicates on the plate (**replicates**)
* Positional information of samples on the plate (**samples**)
* Positional information of genes tested on the plate (**genes**)  
* Raw data from the light cycler containing the Ct values per well (**data**)

The example data was acquired using QuantStudio 7 (384 well plate). When adapting this script, make sure to work with the same format (384 well). In case of using a different format (e.g. 96 well), you will have to change the import options accordingly.

## Analysis details

The workflow consists of 3 steps:  

1. **Data import and formatting**: for easy implementation, the experimental data is imported directly from an Excel file containing the 5 sheets: *condition*, *replicates*, *samples*, *genes* and *data*.  
  
2. **Data analysis**: this includes (**A**) calculation of normalized gene expression, (**B**) calculation of ∆∆Ct and Log2FoldChange per sample and (**C**) selection of adequate statistics using a decision tree.  

3. **Plotting**: visualization of data using ggplot2 with the results from the statistical tests indicating group differences.