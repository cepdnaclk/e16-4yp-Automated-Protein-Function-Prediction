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

The early techniques for predicting protein function have been experimental. Normally, they focused on a specific target gene or protein. Experimental procedures for protein function prediction are very low throughput and are thus unable to annotate a significant fraction of proteins that are becoming available due to rapid advances in genome sequencing technology. This has motivated the development of computational techniques that utilize a variety of high-throughput experimental data for protein function prediction, such as protein and genome sequences, gene expression data, protein interaction networks, and phylogenetic profiles.

The main target of the project was to create an accurate prediction model that assigns the best sub-graph of the gene ontology to each new protein and output a prediction score for this sub-graph and/or each predicted term. There are 

## Related works

## Methodology

### Data set preparation
The machine learning models were trained with the protein sequence data and the Protein-Protein interactions data.Below is the methodology followed for preparation of these data. 

#### Preparation of Sequence Data

* Used [CAFA3 training dataset](https://biofunctionprediction.org/cafa-targets/CAFA3_training_data.tgz). It contains :
    * uniprot_sprot_exp.fasta contains protein sequences of all experimentally annotated proteins, downloaded from the UniProt database in September 2016.Only Swiss-Prot (reviewed) sequences are included (in the fasta format). 
    * uniprot_sprot_exp.txt  contains GO terms with their ontology details

        The experimental annotations (class labels) for these proteins are available in this file in the format: where indicates one of the three GO ontologies: F: molecular function, P: biological process, C: cellular component

    * Combined the data in two files using accession number of proteins and split the data into 3, based on GO ontologies
* Seperated the dataset into ontologies which created separate dataset for each ontology
* The above created dataset divided into species using the taxID created separate datasets for each species.


##### Propagation of GO terms
The ancestors of each GO term was propagated using *[go-basic.obo](http://purl.obolibrary.org/obo/go/go-basic.obo)* file , and added to GO term list in the dataset. The obsolete GO terms were removed.

#### Preparation of Protein-Protein interactions data(PPI)
* Prepared the list of proteins in CAFA3 training data set (list of uniprot identifiers).
* The database that used for collecting PPI data is [STRING](https://string-db.org/) database. 
* STRING ID mappings for the Uniport IDs of the protein list created using the [STRING API] ( https://string-db.org/help/api/ ). (Enviornment python3). 
* With the collected data PPI input matrix created with the association scores.


### Combining CNN and RNN

#### Overview

The analysis of combining CNN and RNN is a crucial area of research for solving problems in the field of Automatic Function Prediction (AFP) for proteins. AFP involves identifying the function of proteins automatically, without human intervention, and has numerous applications in various fields, including biotechnology, medicine, and drug discovery.

From a literature review, it has been found that CNN is often used for AFP and has shown relatively high performance in approaches that use CNN. CNNs are deep learning models that are widely used for image processing tasks. They have also been applied to protein sequence analysis, where they have been shown to outperform other methods in terms of accuracy and computational efficiency.

RNN, on the other hand, is also suitable for solving this problem. RNNs are a type of neural network designed to process sequential data by maintaining an internal memory of previous inputs. They have been widely used for tasks such as protein sequence analysis, where the sequence of amino acids in a protein plays a critical role in determining its function.

To understand the effect of using CNN and RNN separately for solving the AFP problem for proteins, an analysis can be performed. This analysis will help identify the strengths and weaknesses of each method and which approach is better suited for the problem at hand.

In addition, an analysis can also be conducted to understand the effect of combining CNN and RNN. The analysis can be based on the method used to combine the CNN and RNN components of the model. There are various methods for combining CNN and RNN, such as concatenation, addition, and attention. Each method has its strengths and weaknesses, and the performance of the model can vary depending on the method used.

In conclusion, an analysis of combining CNN and RNN can provide valuable insights into the strengths and weaknesses of each method and which approach is better suited for the AFP problem for proteins. It can also help identify the best method for combining CNN and RNN based on the problem at hand, leading to the development of more accurate and efficient models for Automatic Function Prediction in proteins. The application of these methods can improve our understanding of proteins and lead to the development of new drugs and treatments for various diseases. The analysis of CNN and RNN can make significant contributions to the field of biotechnology, and it will continue to be an area of active research for years to come.

#### Combining methods

Combining multiple models is a common approach used to improve the accuracy and reliability of predictions in machine learning. In some cases, a single model may not be able to capture all of the complexities of a problem, and combining several models can provide a more accurate and robust solution. In this article, we will discuss the two methods for combining models that we experimented on: ensemble methods and concatenating feature vectors.

Ensemble methods are a type of machine learning technique that involve combining multiple models to generate a final prediction. One of the simplest and most commonly used ensemble methods is the averaging method. In this method, the predictions of multiple models are averaged together to generate a final prediction. This method works well when the models being combined have similar accuracy and perform well on different parts of the data.

Another commonly used ensemble method is the weighted average method. In this method, each model's predictions are weighted based on their relative performance. Models that perform better on the data receive higher weights, while models that perform poorly receive lower weights. This method can lead to better performance when the models have different strengths and weaknesses.

Concatenating feature vectors is another method for combining models. In this method, the features generated by multiple models are concatenated into a single vector, and this vector is used to generate the final prediction. This method is often used when the different models generate features that are complementary to each other. For example, one model may focus on identifying visual features in an image, while another model may focus on identifying textual features in the same image. By combining the features generated by these models, the final model can capture more of the relevant information.

There are several benefits to using a combination of models. One of the main benefits is increased accuracy. By combining multiple models, the final model is able to capture a broader range of features and information, leading to more accurate predictions. In addition, combining models can also improve the robustness of the final model. By using multiple models, the final model is less likely to be affected by noise or errors in the individual models.

However, there are also some challenges associated with combining models. One challenge is the potential for overfitting. If the models used for combination are highly correlated, the final model may simply be combining noise rather than useful information. Another challenge is the computational cost. Combining multiple models can require significant computing resources, which may be a limitation in some applications.

In conclusion, combining multiple models is a powerful approach for improving the accuracy and robustness of machine learning models. Ensemble methods and concatenating feature vectors are two popular methods for combining models, each with their own strengths and weaknesses. While there are some challenges associated with combining models, the benefits of increased accuracy and robustness make it a worthwhile technique to consider in many machine learning applications.


### Integrating Protein Sequence data and Protein-Protein Interaction data

#### Overview

Protein sequence and protein-protein interactions play an important role in automatic function prediction (AFP) for proteins. In our study, we integrated both protein sequence and protein-protein interaction data to improve the accuracy of our AFP model. Protein sequence provides valuable information about the protein's primary structure, while protein-protein interactions provide insight into the protein's functional associations and potential pathways

## Experiment Setup and Implementation

Accordingly we developed multiple models as follows and experimented on them with Yeast data.

1. CNN baseline
2. Seq-CNN
3. Seq-RNN
4. Ensemble Seq (average of Seq-CNN and Seq-RNN)
5. Seq-CNN-RNN-vectConcat (concatenated feature vector)
6. Seq-CNN-RNN-layerMixed (Mixed CNN RNN layers)
7. PPI-RNN
8. Integrated model version 1

The table below contains the essential details of the above models.

| Model                                                 | Input/Feature     | Architecture                                 | Combining methods             |
|-------------------------------------------------------|-------------------|----------------------------------------------|-------------------------------|
| CNN baseline                                          | Protein Sequence  | CNN                                          | -                             |
| Seq-CNN                                               | Protein Sequence  | CNN                                          | -                             |
| Seq-RNN                                               | Protein Sequence  | RNN                                          | -                             |
| Ensemble Seq (average of Seq-CNN and Seq-RNN)         | Protein Sequence  | CNN + RNN                                    | Average Ensembling            |
| Seq-CNN-RNN-vectConcat (concatenated feature vector)  | Protein Sequence  | CNN + RNN                                    | Concatenating feature vectors |
| Seq-CNN-RNN-layerConcat (concatenated CNN RNN layers) | Protein Sequence  | CNN + RNN                                    | Mixing layers of CNN and RNN  |
| PPI-RNN                                               | PPI               | RNN                                          | -                             |
| Fully Integrated model(version 1)                     | Protein Sequence + PPI | CNN + RNN         | Average Ensembling (in sequence component),Concatenating feature vectors|



## Results and Analysis

## Conclusion
* Ensemble Seq model shows the highest performance over the other above tested sequence only methods for YEAST species.
* PPI data combined methods has improved performance than the sequence only methods.

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
