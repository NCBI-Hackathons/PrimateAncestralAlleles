# ApeShape
### A Project endeavors to find the ancestral states of genetics variants provided by database.

## Please cite our work -- Citation coming soon

![alt text](https://i.pinimg.com/736x/c7/9e/77/c79e77061058fe2f14bb22225be441a1.jpg)

### This pipeline finds ancestral states of each polymorphic site in clinVar (Test case).
The project can be used to study the evolution of genome since it is able to find the ancestral states of a large number of genetic variants. 

### Finding the ancestral states of a large number of genetic variants (provided by database or user).


### The results provided by this project will give researchers a large number of ancestral states data which helps them with their researches.

# Workflow
![alt text](https://github.com/NCBI-Hackathons/PrimateAncestralAlleles/blob/master/workflow.png?raw=true)

# How to use <this software>

## Data Preparation
The data_preparation.R can gather chromosome numbers and SNP postions from NCBI .vcf file. The .bed file generated should be feeded to https://genome.ucsc.edu/cgi-bin/hgCustom. In the website, you should click "Add custom track". The page will be directed to a place where you can upload your file.
After your file is uploaded, a page like this:

![alt text](https://github.com/NCBI-Hackathons/PrimateAncestralAlleles/blob/master/Customtrack.png?raw=true) 

should appear, and you can select it and choose view in tabe browser.

Now you will enter this page

![alt text](https://github.com/NCBI-Hackathons/PrimateAncestralAlleles/blob/master/tablebrowser.png?raw=true)

In 'Output format section choose 'sequence', and type in a file name in 'output file' section. Click 'get output' and a file will start to download. This is the sequence file prepared for BLAST.
  
  ## BLAST
  A custom blast database was created using the reference genomes of Human, Gorilla, Chimpanzee, Orangutan, and Macaque monkey. Using blastn, we found sequences that were similar in all of the chosen organisms. For our analysis, we chose to only keep homologs, however a future analysis could involve the use of paralogs. 
  
  ## Clustal
  Clustal was used to align the sequences that were found during the blast search. This was done to allow for the creation of the phylogeny tree in the next step
  
  ## Phangorn
  The R package Phangorn was used to determine the ancestral allele from the now alligned sequences 

