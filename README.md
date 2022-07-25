___
# Automated Protein Function Prediction Using Machine Learning Techniques
___

[comment]: # "## Please refer the instructions in below URL:"

[comment]: # "https://projects.ce.pdn.ac.lk/docs/how-to-add-a-project"

## Aim

The concept of protein function is highly context-sensitive and not very well-defined hence it acts as an umbrella term for all types of activities that a protein is involved in, be it cellular, molecular or physiological. Accordingly, several functional schemes have been proposed that were expected to have wide coverage, standardized format, hierarchical structure, disjoint categories, multiple functions, dynamic nature etc.
There are a few biomedical ontologies describing protein function. Here we are mostly interested in those representations developed by the Gene Ontology (GO) Consortium.
The Gene Ontology (GO) provides a controlled vocabulary to classify the attributes of proteins based upon representative terms, referred to as “GO terms”. The GO system divides protein attributes into three main categories: molecular function (MF), biological process (BP) and cellular component (CC). Each GO term represents a unique functional attribute and all terms are associated to each other in a directed acyclic graph (DAG) structure based on inheritance relationships.
The primary aim of this project is to come up with an implementation/system/model to accurately predict protein function (a list of Gene Ontology terms) for a given protein sequence. Accordingly, we expect to create an accurate prediction model that assigns the best sub-graph of the gene ontology to each new protein and output a prediction score for this sub-graph and/or each predicted term.

## Background

Protein function prediction is one of the significant tasks of bioinformatics that can help in a wide range of biological problems such as understanding disease mechanisms or finding drug targets. Automated protein function prediction is critical for the annotation of uncharacterized protein sequences, where accurate prediction methods are still required. 
The early techniques for predicting protein function have been experimental. Normally, they focused on a specific target gene or protein, or a small set of proteins forming natural groups such as protein complexes. Experimental procedures for protein function prediction are very low throughput and are thus unable to annotate a significant fraction of proteins that are becoming available due to rapid advances in genome sequencing technology. This has motivated the development of computational
techniques that utilize a variety of high-throughput experimental data for protein function prediction, such as protein and genome sequences, gene expression data, protein interaction networks, and phylogenetic profiles.
This project will develop computational methods based on machine learning that can directly predict the set of GO terms for a given protein including models that can directly extract protein-function associations from biomedical literature. This accurate annotation of protein functions is the key to understanding life at the molecular level and has great biomedical and pharmaceutical implications


## Expected Outcomes


