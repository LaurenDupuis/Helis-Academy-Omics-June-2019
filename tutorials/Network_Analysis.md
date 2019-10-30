# Network Analysis
# Using network analysis to study the molecular and regulatory mechanisms involved in lung cancer
==================================================================================================
## June 13, 2019
## Practical prepared by: Dr. Martina Summer-Kutmon and Dr. Lauren Dupuis
---------------------------------------------------------------------------------------------------

In this part, we want to show you different ways of how you can build biological network relevant for a biological research topic. 
Cytoscape has a lot more functionality and you are free to explore other apps in the project if you want to.  

### Assignment 1: Drug targets in the cell cycle pathway

Using the cell cycle pathway, you will learn how pathways can be used as a resource for network biology. Besides looking at the network 
structure, we will also add drug-target information to see which drugs in the DrugBank database are known to target genes in the cell 
cycle pathway.

Before beginning, make sure the WikiPathways App is installed. Click “Apps” - “App Manager”. Search for WikiPathways and click “Install”. 
Do the same for “stringApp”.

![Figure 1](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Figure_1_NA.png?raw=true)

Now we can begin by importing the Cell Cycle Pathway as a network.
•	Go to “File - Import - Network From Public Databases”
•	A dialog box will appear. Change the Data Source dropdown box to “WikiPathways”. Search for “Cell Cycle”. Click the check box for 
“Only:”, and choose “Homo sapiens” in the dropdown box. 
•	Select “Cell Cycle” from the list and click “Import as Network”

![Figure 2](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Figure_2_NA.png?raw=true)

•	You should now see a network with 164 nodes and 223 edges.

> **Question 1A**	Are all nodes connected or do you see subnetworks or unconnected nodes? Make a screenshot.

Now we are going to investigate which drugs are known to target the proteins in this pathway.
•	Go to “Apps → CyTargetLinker → Extend network”
•	Fill in the following settings: 

![Figure 3](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Figure_3_NA.png?raw=true)

•	Now the known drugs from DrugBank have been added – information about drug name, drug category or approval status can be found in the 
node table.
•	If you go to “Apps → CyTargetLinker → Show Result Panel”, you can see how many drugs were added (on the right side of the screen). 
You can find more information about the drugs on the [DrugBank website](www.drugbank.ca) to investigate if any of the drugs are used 
for lung cancer treatment.  The identifiers and names of the drugs can be found in the node table below the network. 

> **Question 1B** How many drugs were added to the network?

> **Question 1C**	Which genes are targeted by many drugs?
----------------------------------------------------------------------------------------------------------------------

### Assignment 2: Build network for up-regulated lung cancer genes

#### **Step 1: Gene selection**
•	Open the dataset (lung-cancer-data.xlsx) in Excel. 
•	Select the significantly up-regulated genes with a log2FC > 1 → filter the table by log2FC (>1) and the adju.P.Value (< 0.05). 
•	Copy the Ensembl IDs of the 408 genes.
#### **Step 2: Create PPI network for gene selection**
•	In Cytoscape, go to the Control Panel and select the STRING protein query (drop-down box left to search field) and paste the 408 gene 
names in the query field 

![Figure 4](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Figure_4_NA.png?raw=true)

•	Click on the search icon.
•	Cytoscape will create a network with 368 nodes and 1,678 edges

> **Question 2A** Are all nodes connected or do you see subnetworks or unconnected nodes?

•	Select the largest connected subnetwork (click shift and select the area of the subnetwork with the computer mouse). Go to File - 
New Network - From selected nodes, all edges.
•	A new network will be created only containing the largest connected subnetwork with 244 nodes and 1,665 edges.

#### **Step 2: Investigate the network properties of the network**
•	Go to “Tools → Network Analyzer → Network Analysis → Analyze Network...”
o	The network should be treated as an undirected network (protein-protein interactions, in general, do not have a direction)
•	This tool will calculate all network properties like degree and betweenness for you.

> **Question 2B** What are node degree and node betweenness? Describe in your own words

> **Question 2C** Look at the “Node degree” and “Node betweenness” tab in Results panel of the Network Analyzer. How are node degree 
> and betweenness distributed in this network? Do the distributions make sense? Are there any interesting observations?

#### **Step 3: Create visualization to show disease score and degree**
•	In the NetworkAnalyzer result dialog, click on “Visualize Parameters”. Select the node degree as node color gradient (Map node color 
to → Select “Degree”) and the node betweenness as node size.

![Figure 5](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Figure_5_NA.png?raw=true)

> **Question 2D** Describe the overall network visualization. Large nodes have a high betweenness and the redder the node, the higher 
> the degree.

> **Question 2E** Can you find any hub nodes? (Hint: columns in Cytoscape are sortable by clicking on the header)
> CCNA2 has highest degree. 

#### **Step 4: Find more information about major hub gene**
There is one gene attracting attention due to a very high degree and betweenness (Question 9c). The human protein atlas is an exceptional 
resource to find out more information about the expression of a gene/protein in different tissues but it also provides detailed pathology 
analysis for relevant cancer genes. 
•	Go to the [protein atlas](https://www.proteinatlas.org) 
•	Search for CCNA2 - hub gene of our previous network
•	In the pathology tab, you can find information about the prognostic summary for different cancers, the RNA expression overview using 
data from TCGA, and show staining of the protein in different samples. 

> **Question 2F** What kind of additional information can you find about CCNA2 in relation to lung cancer (click on the Pathology tab 
> for the gene entry)?






