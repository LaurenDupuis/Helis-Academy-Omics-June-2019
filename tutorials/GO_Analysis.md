# Gene Ontology Analysis Practical 
==============================================================
## 12 June, 2019
## Practical prepared by Dr. Martina Summer-Kutmon, Dr. Lars Eijssen, and Dr. Lauren Dupuis
------------------------------------------------------------------------------------------------

### Introduction

Gene Ontology (GO) provides a structured and controlled vocabulary to describe gene products in terms of their associated biological 
processes, cellular components and molecular functions. One of the main uses of GO is to perform functional enrichment analysis on gene sets. 

For GO analysis, we need two different gene lists:
1.	Target gene set - we selected upregulated genes in the dataset with logFC > 1 and a significant p value
“upregulated_genes.txt” 
2.	Background set - complete list of measured genes in the dataset - 
“background_genes.txt” 

---------------------------------------------------------------------------------------------------------------------

### Assignment:	Perform gene ontology analysis with GOrilla

1.	Go to the [GOrilla tool](http://cbl-gorilla.cs.technion.ac.il/). 
2.	Step 1: Select “Homo sapiens”
3.	Step 2: Select “Two unranked lists of genes (target and background lists)”
4.	Step 3: Upload files for target genes set and background set:
“upregulated_genes” and “background_genes.txt”
5.	Step 4: Select “Process”
6.	Click “Search Enriched GO terms”

> **Question 1** You will now see the GO tree with the p-values colored on the process nodes. If you scroll down you can also see a table 
> of enriched GO processes. What are the top 10 GO classes?

> **Question 2** Can you find processes expected to be altered due to lung cancer (biological interpretation)?  

> **Question 3** The results of the pathway analysis in (see question 4B) and the GO analysis (see question 5A) both show a list of 
> affected biological processes obtained with different analysis methods. Do you see overlap (similar processes) between the pathway 
> statistics result and the GO analysis result? If yes, give one example.
