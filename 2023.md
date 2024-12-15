The growth and evolution of our civilization have been based on the use of biodiversity. Human survival was much sustained by the use of plant species, especially for nutrition and medicinal uses. Natural products are the most traditional source for the design and development of new drugs. Taking into account all drugs approved worldwide, 67% are either a natural product, semi-synthetic derivative, macromolecule isolated from an organism or have a pharmacophore group inspired by a natural product. Natural products researchers have been studying the medicinal properties of plants, and great advances regarding biosynthesis, ecology, and biological properties were achieved in the last century. Unfortunately, many species are endangered of extinction, and their chemistry, genes, and biological properties would also be lost. 

The knowledge of over 50 years of studies on biodiversity available in scientific articles can become easier accessible when organized and shared through knowledge graphs. It can assist in the development of different fields of science and bio-friendly products with high added value as well as guide public policies to bring benefits both to science and to strengthen the bio-economy. All these benefits demonstrate the need for organized and standardized policies and procedures to produce high-quality and valuable information. In this sense, the Semantic Web architecture choices can facilitate the publishing, sharing, and consuming of this valuable information among researchers and leading institutions. Once the data is in the RDF format, contributions from the wide range of the so-called Linked Data fields such as knowledge discovery, machine learning, data fusion, information retrieval, and data quality can help to foster sustainable growth of biochemical data as well as facilitate harvest all its potential to a more environmentally conscious society. 

However, to date, most of the structured biochemical information available on the Web is manually curated, and it is practically impossible to keep pace with the research being constantly published in scientific articles. Within this challenge, we want to speed up and promote research on automatic biochemical knowledge extraction mechanisms by the Semantic Web scientific community to increase the information available on natural products to promote the development of environmental-friendly products while increasing the community's awareness of the biodiversity value.


# Pre-registration

We encourage participants to perform a pre-registration to keep informed about any changes on the program.
Pre-registrations can be performed through the online form: [https://forms.gle/2sMUUondkULRwnE66](https://forms.gle/2sMUUondkULRwnE66)

# [Challenge](https://aksw.github.io/bike/#challenge)

We invite researchers to participate by re-using or designing new innovative Biochemical Extraction methods. 
The participants will have the opportunity to present, discuss and display their knowledge extraction approach at the BiKE workshop.
The Challenge consists in extracting relevant information from a set of biochemical research articles and constructing a knowledge graph through a given ontology.

## Training Data set

The dataset used for evaluation and training was generated from hundreds of peer-reviewed scientific articles with information on more than 2,521 possibilities of natural product extraction. 
The dataset was built manually by chemistry specialists that read the articles annotating four relevant properties associated with each natural product discussed in the academic publication.
For this challenge, we focus on five NuBBE properties for training and prediction: (I) compound name ([rdfs:label](http://www.w3.org/2000/01/rdf-schema#label)), (II) bioactivity ([nubbe:biologicalActivity](http://nubbe.aksw.org/ontology/index.html#d4e142)), (III) species from where natural products were extracted ([nubbe:collectionSpecie](http://nubbe.aksw.org/ontology/index.html#d4e227)), (IV) collection site of these species ([nubbe:collectionSite](http://nubbe.aksw.org/ontology/index.html#d4e206)), and (V) isolation type ([nubbe:collectionType](http://nubbe.aksw.org/ontology/index.html#d4e248})).
The table below presents an overview of the number of unique properties.

All papers are present on all train splits, but the papers selected for each test split have all links to manually extracted characteristics removed.
This means that these papers will not be connected to the rest of the knowledge graph.
The provided code for generating the knowledge graph representation with python's networkx uses BERTopic's extracted topics for reconnecting the knowledge graph.
The assigned topics are also filtered by the following rule: if the topic is present in more than 80% of examples it is eliminated since it does not discriminate from the others.
Part of the challenge is to figure out other ways to reconnect the knowledge graph with automatically extracted characteristics like citation networks for the authors, conferences, and others.

We provide the original flat data and the original networkx knowledge graph.
We also provide 10 previously randomized train/test splits that contain the links maintained and removed, respectively.
For every train/test split, we also provide a prepared networkx knowledge graph.
The provided data can be accessed here: [https://drive.google.com/drive/folders/1NXLQQsIXe0hz32KSOeSG1PCAzFLHoSGh?usp=sharing](https://drive.google.com/drive/folders/1NXLQQsIXe0hz32KSOeSG1PCAzFLHoSGh?usp=sharing)
The source code and documentation for NatUKE can also be accessed at: [https://github.com/AKSW/natuke](https://github.com/AKSW/natuke)

For referencing the benchmark used please refer to:

```
@inproceedings{icsc/natuke/2023,
  title = {NatUKE: A Benchmark for Natural Product
    Knowledge Extraction from Academic Literature},
  author = {Paulo Viviurka do Carmo,
    Edgard Marx,
    Ricardo Marcacini,
    Marilia Valli,
    João Victor Silva e Silva,
    Alan Pilon},
  booktitle = {17th IEEE International Conference on Semantic Computing},
  year = {2023},
  publisher = {IEEE}
}
```

## Evaluation Metrics

We are interested in ranking the correct document prediction of real links that were hidden in the knowledge graph.
Together with MRR (Mean Reciprocal Rank), hits@k is a ranking metric for when there is only one correct document.
On the other hand, mAP (mean Average Precision) and nDCG (normalized Discounted Cumulative Gain) are designed for ranking when a list of relevant documents is available.
We chose hits@k because it allows us to evaluate each characteristic extraction with reasonable expectations by customizing the k value.
Following the rule used in NatUKE the final k values in this table are from 1 to 50 considering values multiples of 5 and two thresholds: (1) a score equal or higher than 0.50 is achieved; and (2) a score equal or higher than 0.20 is achieved.
Please refer to the NatUKE benchmark paper for further details.

# [Submission guidelines](https://aksw.github.io/bike/#challenge)

On 12th of February, we decided to split the submission into two stages (1) results and (2) papers.

## Rules

- Every competing team should submit their results using the paper template.

- The only information mandatory in the result submission is as follows:
  - A table containing the performance of your approach in comparison with the baseline;
  - A link to an open repository containing the code used for training and all the necessary resources, including files and pre-trained models to replicate the results;
  - Title, Authors, and respective affiliations;
  - To facilitate your result submission, we prepared a template: [https://www.overleaf.com/read/zcbppmhfkbpd](https://www.overleaf.com/read/zcbppmhfkbpd)

## Paper

- Every competing approach should submit a 12 pages article written in English describing the method in the style of the Springer Publications format for Lecture Notes in Computer Science (LNCS). For further instructions, you can check the Springer Conference Proceeding templates at [Springer submission guidelines](https://www.springer.com/de/it-informatik/lncs/conference-proceedings-guidelines).

- Paper Overleaf Template: [https://www.overleaf.com/read/zcbppmhfkbpd](https://www.overleaf.com/read/zcbppmhfkbpd)

- All submissions will be peer-reviewed by the Program Committee. 

- The accepted contributions will be evaluated based on their quality and published in the proceedings of the workshop. 

- Each competing approach needs to be registered and presented by one of the authors at the workshop (presentations can be held online). Not complying with this rule may lead to disqualification.

- All papers should be submitted to easychair under the following link  [https://easychair.org/conferences/?conf=bike2023](https://easychair.org/conferences/?conf=bike2023).

# [QA](https://aksw.github.io/bike/#qa)

To help participants to get on board, we created a QA channel on Slack, you can post your questions directly there: 
- [https://join.slack.com/share/enQtNTIxNjc5NDE3Nzg0Ni1lYTdmZTU2ODA3MmRlMTgzZjMzMDhlM2FjNmIyNDU1YWVkMTBiNjAwMjNlNjlkODM5NjA0NjgxNjMxZDgyNDA2](https://join.slack.com/share/enQtNTIxNjc5NDE3Nzg0Ni1lYTdmZTU2ODA3MmRlMTgzZjMzMDhlM2FjNmIyNDU1YWVkMTBiNjAwMjNlNjlkODM5NjA0NjgxNjMxZDgyNDA2)

# [Contact](https://aksw.github.io/bike/#contact)

- edgard.marx@htwk-leipzig.de

# [Agenda](https://aksw.github.io/bike/#agenda)

- Release of training data and instructions: Friday, January 20th, 2023 PST
- **(extended)** Result submission deadline: ~~April 27th, 2023 PST~~ **May 19th, 2023 PST**
- **(extended)** Release of test dataset & results: ~~April 7th, 2023~~ **May 28th, 2023 PST**
- **(extended)** Paper submission deadline: ~~February 28th, 2023~~ **June 20th, 2023 PST**
- **(extended)** Notification & Reviews: ~~March 28th, 2023~~ **June 30th, 2023 PST**
- **(extended)** Submission of camera-ready papers: ~~April 11th, 2023~~ **July 17th, 2023 PST**
- Workshop at ESWC: ***28.05.2023***

# [Awards](https://aksw.github.io/bike/#awards)

The first, second, and third best biochemical knowledge extraction methods are going to be awarded as follows:

- ``First Place``: EUR 1000
- ``Second Place``: EUR 500
- ``Third Place``: EUR 250

# [Program](https://aksw.github.io/bike/#program) 

## 28.05.2023

### 08:30 - Registration

- 08:30 - Registration at the Conference

### 09:00 - Welcome (Edgard Marx)

**Towards Natural Inspired Products from Biodiversity** by Edgard Marx (Project Manager at the [HTWK](https://www.htwk-leipzig.de/) and Linked Data Expert at [eccenca](https://www.eccenca.com/))

### 09:30 - Session 1 (Chair: Edgard Marx)

- 09:30 - **NaTUKE: A Benchmark for Natural Product Knowledge Extraction from Academic Literature** by Paulo Ricardo Viviurka do Carmo (Researcher at HTWK, Germany)
- 09:50 - **The NuBBE Knowledge Graph: A Biochemical Knowledge Graph of Natural Products from Brazilian Biodiversity** by István J. Mócsy (Researcher at HTWK, Germany)
- 10:10 - **Improving natural product automatic extraction with named entity recognition** by Stefan Schmidt-Dichte and István J. Mócsy (HTWK, Germany)

### 10:30 - Coffee Break

### 11:00 - Session 2 (Chair: Paulo do Carmo)

- 11:00 - **Enhancing Biochemical Extraction with BFS-driven Knowledge Graph Embedding approach** by Bhushan Zope, Sashikala Mishra and Sanju Tiwari (SIU, India)
- 11:20 - **BiKE Challenge: Result of ChemiScope by using ChatGPT** by Matthias Jooß, Jonas Gwozdz and Pit Fröhlich (HTWK, Germany)
- 11:40 - **Awards**

### 12:00 - Lunch

# [Results](https://aksw.github.io/bike/#results)

### First Place:

- **BiKE Challenge: Result of ChemiScope by using ChatGPT** by Matthias Jooß, Jonas Gwozdz and Pit Fröhlich (HTWK, Germany)

### Second Place:

- **Improving natural product automatic extraction with named entity recognition** by	Stefan Schmidt-Dichte and István J. Mócsy (HTWK, Germany)

### Third Place:

- **Enhancing Biochemical Extraction with BFS-driven Knowledge Graph Embedding approach** by Bhushan Zope, Sashikala Mishra and Sanju Tiwari (SIU, India)

# [Organizing Committee](https://aksw.github.io/bike/#organizing-committee)

### General Chair

Edgard Marx, HTWK, Germany

### Organizing Committee

Sanju Tiwari, UAM, Mexico

Joao Victor da Silva e Silva, USP, Brazil

Marilia Valli, USP, Brazil

Paulo Ricardo Viviurka do Carmo, HTWK, Germany

### Advisory Committee

Vanderlan da Silva Bozani, UNESP, Brazil

Adriano Defini Andricopulo, USP, Brazil

Thomas Riechert, HTWK, Germany

Alan Pilon, USP, Brazil
