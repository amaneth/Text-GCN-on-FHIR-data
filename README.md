# Text-GCN-on-FHIR-data
Text-GCN on FHIR
====
This project is about adapting the Text Graph Convolutional Network(Text-GCN) to FHIR data classification problem. FHIR(Fast Healthcare Interoperability Resources) is a standard describing data formats and elements and an application programming interface for exchanging electronic health records. The standard was created by the Health Level Seven International health-care standards organization. This project uses the technique explained in the Text-GCN paper to leverage the fhir data.  Text-GCN is about building a large and heterogeneous text graph which contains word nodes and document nodes so that global word co-occurrence can be explicitly modeled and graph convolution can be easily adapted, as shown in Figure below. The number of nodes in the text graph |V | is the number of documents
(corpus size) plus the number of unique words (vocabulary size) in a corpus. The weight of the edge between a document node and a word node is the term frequency-inverse document frequency (TF-IDF) of the word in the document. It also uses point-wise mutual information (PMI), a popular measure for word associations, to calculate weights between two word nodes. The task in this project is a simple multiclassification task which predicts the condition from the procedure and the medication. Text-GCN is adapted to this project in way that the documents are medication and procedure information of the patient merged and the word nodes are the the medication and proeceure informations of each patient.  A lower number sliding windows is also used in the PMI calculation. The synthetatically generated data from synthea is used to train the GCN model. 

![Text Graph Convolutional Networks](imgs/text_gcn.png)

This implementation makes use of the Cora dataset from [2].


## Requirements

  * PyTorch 0.4+
  * Python 3.6+


## References
[1] [Liang Yao, Chengsheng Mao & Yuan Luo, Graph Convolutional Networks for Text Classifications, 2018](https://arxiv.org/abs/1809.05679)

[2] [Kipf & Welling, Semi-Supervised Classification with Graph Convolutional Networks, 2016](https://arxiv.org/abs/1609.02907)


