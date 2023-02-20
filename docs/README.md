---
layout: home
permalink: index.html

# Please update this with your repository name and title
repository-name: e16-4yp-Automated-Protein-Function-Prediction
title: Automated Protein Function Prediction Using Machine Learning Techniques
---

[comment]: # "This is the standard layout for the project, but you can clean this and use your own template"

# Automated Protein Function Prediction Using Machine Learning Techniques

#### Team

- E/16/290, Kalani Prabodha, [email](mailto:e16290@eng.pdn.ac.lk)
- E/16/267, Wasana Parackrama, [email](mailto:e16267@eng.pdn.ac.lk)
- E/16/096, Dulmini Ekanayake, [email](mailto:e16096@eng.pdn.ac.lk)

#### Supervisors

- Dr. Damayanthi Herath, [email](mailto:damayanthiherath@eng.pdn.ac.lk)
- Dr. Indika Kahanda, [email](mailto:indika.kahanda@unf.edu)

#### Table of content

1. [Abstract](#abstract)
2. [Related works](#related-works)
3. [Methodology](#methodology)
4. [Experiment Setup and Implementation](#experiment-setup-and-implementation)
5. [Results and Analysis](#results-and-analysis)
6. [Conclusion](#conclusion)
7. [Publications](#publications)
8. [Links](#links)

---

[comment]: # "This is a sample image, to show how to add images to your page. To learn more options, please refer [this](https://projects.ce.pdn.ac.lk/docs/faq/how-to-add-an-image/)"

[comment]: # "![Sample Image](./images/sample.png)"

## Abstract

Protein function prediction is one of the significant tasks of bioinformatics that can help in a wide range of biological problems such as understanding disease mechanisms or finding drug targets. 

The concept of protein function is highly context-sensitive and not very well-defined hence it acts as an umbrella term for all types of activities that a protein is involved in, be it cellular, molecular or physiological. Accordingly, several functional schemes have been proposed that were expected to have wide coverage, standardized format, hierarchical structure, disjoint categories, multiple functions, dynamic nature etc. 

There are few such biomedical ontologies describing protein function, and the representations developed by the Gene Ontology (GO) Consortium is widely popular by now. The Gene Ontology (GO) provides a controlled vocabulary to classify the attributes of proteins based upon representative terms, referred to as “GO terms”. The GO system divides protein attributes into three main categories: molecular function (MF), biological process (BP) and cellular component (CC). Each GO term represents a unique functional attribute and all terms are associated to each other in a directed acyclic graph (DAG) structure based on inheritance relationships.Automated protein function prediction is critical for the annotation of uncharacterized protein sequences, where accurate prediction methods are still required.

The early techniques for predicting protein function have been experimental. Normally, they focused on a specific target gene or protein, or a small set of proteins forming natural groups such as protein complexes. Experimental procedures for protein function prediction are very low throughput and are thus unable to annotate a significant fraction of proteins that are becoming available due to rapid advances in genome sequencing technology. This has motivated the development of computational
techniques that utilize a variety of high-throughput experimental data for protein function prediction, such as protein and genome sequences, gene expression data, protein interaction networks, and phylogenetic profiles.

The accurate annotation of protein functions is the key to understanding life at the molecular level and has great biomedical and pharmaceutical implications. In this particular project, it is planed to develop computational methods based on machine learning that can directly predict the set of GO terms for a given protein including models that can directly extract protein-function associations from biomedical literature. Accordingly, we expect to create an accurate prediction model that assigns the best sub-graph of the gene ontology to each new protein and output a prediction score for this sub-graph and/or each predicted term

## Related works

There were many proposed models for AFP over the past few years to solve these problems. Generally, protein function identification is accomplished through manual or computational annotation. we noticed automated protein function prediction using GO terms ranging from traditional solutions to the most recently developed deep learning-based tools.We noticed the traditional approach representative solutions in three categories: similarity-based methods, probabilistic methods, and machine learning methods.OntoBlast,GOFigure,GOblet,Gotcha,PFP,INGA,GoFDR are some of similarity based methods and BMRF is an example for probabilistic based method.\cite{vu2021protein}

GOPET,PoGO,FFPred3,PANNZER2,DeepText2GO,NetGo are some methods used by machine learning.These methods used Support vector machine (SVM),Weighted K-nearest neighbor classification techniques in their models.\cite{vu2021protein}

When considering future of AFP Machine learning techniques are shown noticeble improvement.Newly identified proteins either lack identifiable sequences or their detectable terms have not been assigned any GO labels.Directly using the annotation from the amino acid sequence, without access to any additional references or databases to assign protein function is an ongoing task.

## Methodology

### Data set preparation
#### Preparation of Sequence Data

- Used the [CAFA3]([https://pages.github.com/](https://biofunctionprediction.org/cafa-targets/)) training dataset .It contains:
   - uniprot_sprot_exp.fasta contains protein sequences of all experimentally annotated proteins, downloaded from the UniProt database in September 2016. Only Swiss Prot sequences are included (in the fasta format). 
   - uniprot_sprot_exp.txt  contains GO terms with their ontology details
The experimental annotations (class labels) for these proteins are available in this file in the format: where indicates one of the three GO ontologies: F: molecular function, P: biological process, C: cellular component
we combine the data in two files using accession number of proteins and split the data into 3, based on GO ontologies
Seperated the dataset into ontologies which created dataset for each ontology
The above created dataset divided into species using the taxID created separate datasets for each species.
Propagation of GO terms
The ancestors of each GO term was propagated using go-basic.obo file , and added to GO term list in the dataset. The obsolete GO terms were removed.

## Experiment Setup and Implementation

## Results and Analysis

## Conclusion

## Publications
[comment]: # "1. [Semester 7 report](./)"
[comment]: # "2. [Semester 7 slides](./)"
[comment]: # "3. [Semester 8 report](./)"
[comment]: # "4. [Semester 8 slides](./)"
[comment]: # " (5. Author 1, Author 2 and Author 3 'Research paper title' (2021). [PDF](./)."


## Links

[//]: # ( NOTE: EDIT THIS LINKS WITH YOUR REPO DETAILS )

- [Project Repository](https://github.com/cepdnaclk/e16-4yp-Automated-Protein-Function-Prediction)
- [Project Page](https://cepdnaclk.github.io/e16-4yp-Automated-Protein-Function-Prediction)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://eng.pdn.ac.lk/)

[//]: # "Please refer this to learn more about Markdown syntax"
[//]: # "https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet"
