---
title: 'MetaboliteNET: building a metabolite centric knowledge base by ontology-based mining annotations from literature'
title_short: 'MetaboliteNET'
tags:
  - Metabolites
  - Text mining
  - Ontologies
  - Knowledge Graphs
authors:
  - name: Núria Queralt-Rosinach
    orcid: 0000-0003-0169-8159
    affiliation: 1
affiliations:
  - name: Human Genetics, Leiden University Medical Center, Leiden, Netherlands
    index: 1
date: 11 February 2023
cito-bibliography: paper.bib
event: BioHackMENA23
biohackathon_name: "BioHackathon-MENA"
biohackathon_url:   "https://cemse.kaust.edu.sa/cbrc/events/event/bio-hackathon-mena-2023"
biohackathon_location: "Thuwal, KSA, 2023"
group: Project 7
# URL to project git repo --- should contain paper.md
git_url: 
# This is the short authors description that is used at the
# bottom of the generated paper.
authors_short: Núria Queralt-Rosinach \emph{et al.}
---
<!--

The paper.md, bibtex and figure file can be found in this repo:

  https://github.com/journal-of-research-objects/Example-BioHackrXiv-Paper

To modify, please clone the repo. You can generate PDF of the paper by
pasting above link (or yours) in

  http://biohackrxiv.genenetwork.org/

-->

# Introduction
Recent estimates in dementia cases projected that the largest increases due to population ageing are observed in east Asia, and north Africa and the Middle East [1]. There is an increasing body of scientific evidence on how natural medicines (i.e. herbal medicines, traditional formulas) and food metabolites are environmental factors that can be used to maintain health or treat multifactorial and chronic diseases such as neurodegenerative diseases [2]. For example, traditional Arabic herbal medicine is a part of modern life in the Middle East, and it is acquiring worldwide respect, with growing interest among traditional herbalists and the scientific community. Traditional medicines represent likely sources of relatively inexpensive drugs for symptomatic management as well as potential libraries of new therapeutic approaches. Plants produce a wide diversity of metabolites that exhibit a wide array of biological and pharmacological properties. The multitarget activities of many metabolites can explain the medical application of complex extracts from medicinal plants, food or even drug metabolites for health disorders that involve several targets. Therefore, the development of a metabolite-centric annotation dataset from literature is useful for the identification of functionally similar metabolites with application in disease biomarker discovery, drug discovery or agriculture. Furthermore, data science pipelines applied on text mining based knowledge graphs have the potential to accelerate understanding on mechanisms and mode of actions, link therapies to new potential target applications, and rapidly accelerate the validation (and exclusion) of traditional medicines [3]. The motivation of this project was to provide a metabolite-centric annotation dataset as a valuable knowledge resource to enhance precision medicine in the MENA region. Here, we present the development of MetaboliteNET a metabolite centric annotation dataset and knowledge graph, built from the literature and existing resources for machine learning prediction of interesting metabolites.

# Results
## Text mining human and plants metabolite-centric annotations 
We extracted human and plant metabolite annotations from the scientific literature and make them publicly available. The metabolite - X extracted associations where X were phenotypes (Human Phenotype Ontology or HPO), diseases (Human Disease Ontology or DO, and Mondo Disease Ontology or MONDO), environmental factors (Environment Ontology or ENVO), anatomical (Uberon multi-species anatomy Ontology or UBERON), cell types (Cell Ontology or CL), gene products functions (Gene Ontology or GO) for human metabolites, and X were ENVO, CL, phenotypes (Flora Phenotype Ontology or FLOPO, and Plant Trait Ontology or PTO), anatomy (Plant Ontology or PO) for plants. The MetaboliteNET annotation dataset was yielded automatically from mining the literature using an in-house annotation tool that performs co-occurrence extraction of mentions (as ontology terms) at abstract level over all MEDLINE, and applies a statistical approach based on ontological structure to determine the association strength [4]. This tool is currently being updated to extract relevant information at mention and publication level. 

## Building MetaboliteNET knowledge graph
The MetaboliteNET annotation data set served as a foundation to build a metabolite-centric knowledge graph for representation learning or curation for corpora development. We build a knowledge graph of size 30,421 nodes and 534,836 edges represented using common ontologies. 

## Investigating its applications
In order to demonstrate the use of MetaboliteNET for discovery we explored three applications of biomedical interest:

### Biomarker discovery
We performed and enrichment analysis of metabolites associated to 4 neurodegenerative diseseas: Motor neuron disease (DOID:231), Huntington’s disease (DOID:12858), Alzheimer’s disease (DOID:10652), and Neurodegeneration with brain iron accumulation (DOID:0110734). We found interesting results supported by evidence in curated databases.  

### Link prediction using the Neo4j data science library
We examined the Neo4j data science suite of tools for data science to perform knowledge graph completion.

### Link prediction using mOWL
In collaboration with mOWL project in the BioHackathon, we investigated the use of machine learning with ontologies to make drug-disease prediction.

### Availability
We published the annotation dataset, knowledge graph, and the analytics workflows for community reuse. Code and workflows available on [GitHub](). We will apply the license Creative Commons Attribution 4.0 International to the annotation data set and the MIT license to the code to enable reusability and reproducibility.

# Discussion
We developed MetaboliteNET a metabolite-centric annotation dataset extracted from PubMed publication abstracts. Then, we represented it as a knowledge graph to be used for predictive analytics and support precision medicine. We started by mining human metabolites to describe human biology and plant metabolites to describe potential drug biology. Finally, we provided three applications to demonstrate its use in data science workflows for translational research.

We aimed at evaluating our text mined data against curated associations. However, due to the limiting time, we put the evaluation of the annotation dataset off after the BioHackathon. This evaluation is key to ensure the quality of the dataset for discovery. The biohackathon provided a suitable environment to gather multidisciplinary researchers of different level of expertise. This fostered interesting discussions and new ideas. In these discussions, we detected an important limitation of our text mining approach and is the lack of precise semantics of the extracted associations. This is due to the current implementation of the system, which lacks of event extraction capability. We plan to add this feature in the future. Another extremely interesting discussion was about the semantic modelling of the knowledge graph. We will examine togoid tool to enrich our graph from curated and interoperable existing knowledge bases. 

Thanks to the diverse ecosystem of researchers and tools of the biohackathon we developed a proof-of-concept of our idea centered on metabolite knowledge and provided open data and tools for the community. All the participants collaborate on the implementation of the different parts of the project. The venue also gave us the perfect setup to develop computation and infrastructure, and build novel collaborations across several continents.

# Future work
* Evaluation of the annotation dataset
* Application for drug repurposing on highly prevalent metabolic rare diseases in the MENA region.
* Expansion with known knowledge such as Wikidata
* Text mine new entities such as drug, food and microbiome metabolites, enzymes, and proteins.
* Prepare a manuscript.

## Contributions
NQR draft the first version of the manuscript, built the knowledge graph, constructed the link prediction workflow based on MOWL. SK produce the annotation dataset. SA prepared ontologies for text mining, extracted a drug-disease curated dataset from HMDB, and constructed the biomarker discovery workflow. Kexin constructed the knowledge graph completion workflow based on Neo4j library. All co-authors participated in discussions and reviewed the manuscript. 

## Acknowledgements
We thank the organisers of the BioHackathon-MENA 2023 for travel support for some of the authors.

## References

