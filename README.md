# project-proposal

Reasoning is an ongoing challenge in IOT.

## General Background Info

### Reasoning Techniques

OWL2 Profiles

 - EL

 - QL

 - RL



## Benchmarking Datasets

 LUBM [5], UOBM [9], BSBM  [3], SP2Bench  [15], DBpedia  [10], and OntoBench  [8]

OWL2Bench reasoners benchmarked
Six reasoners, namely, ELK  [7], HermiT  [4], JFact3, Konclude  [17], Openllet4, and Pellet  [16] - all seem to be using Java.

Plan: Use [JSweet](https://github.com/cincheo/jsweet) to get some existing reasoners that have been developed in JAVA. https://github.com/cincheo/jsweet/blob/master/doc/jsweet-language-specifications.md#packaging-with-modules

### [OWL2Bench](https://link.springer.com/content/pdf/10.1007%2F978-3-030-62466-8.pdf)

Motivation: Need high quality ontology benchmarks that have good coverage of OWL2 Language Constructs.

Tests *scalability*

https://github.com/kracr/owl2bench

### [OntoBench](https://link.springer.com/chapter/10.1007%2F978-3-319-46547-0_13)

OWL2 ontology benchmarking for *coverage*.

### [JustBench](https://link.springer.com/chapter/10.1007%2F978-3-642-17746-0_3)

Tests speed on fixed size dataset

### [ORE](https://link.springer.com/chapter/10.1007%2F978-3-319-46547-0_17)

Ontology Reasoner Evaluation competition


## Other

### [International Description Logic Workshop](http://dl.kr.org/)

# Existing work
## [RDF Reasoning on Large Ontologies: A Study on Cultural Heritage and Wikidata](https://ieeexplore.ieee.org/abstract/document/7881709)

## [Explainable Deep RDFS reasoner](https://arxiv.org/pdf/2002.03514.pdf)

## [Deep Learning for noise-tolerant RDFS reasoning](http://www.semantic-web-journal.net/system/files/swj2186.pdf)

## [Large Scale Incremental OWL/RDFS Reasoning over Fuzzy RDF Data](https://ieeexplore-ieee-org.virtual.anu.edu.au/stamp/stamp.jsp?tp=&arnumber=7881709)

Key ideas:
Noise reduction, handle noise in ABOX relations but *not* in TBOX relations. This is done by only applying noise handling on *certain* rules and graphs.

# Methodology

The [Comunica Engine](https://github.com/comunica/comunica) is a "is a meta query engine using which query engines can be created. It does this by providing a set of modules that can be wired together in a flexible manner." [comunica website](https://comunica.dev/about/). Comunica has built in [benchmarking](https://github.com/comunica/comunica#benchmarking) support.

We are currently working on the development of a [reasoning bus](https://github.com/comunica/comunica-feature-reasoning) for this engine

## Motivation for using Comunica

Comunica is a highly configurable SPARQL query engine that is seeing a growing adoption within the Semantic Web community. Notable projects using this engine include the [solid community server](https://github.com/solid/community-server/blob/main/package.json)

## Key Challenges

## Scalability

### Noise Handling


# Project Outline

*Deadlines in this document are a an internal guideline and should not be treated as a date at which deliverables can be expected*

## Stage 1 - Interface Development (-15/9/2021)

Interface development - develop a generic bus interface for Reasoners on Comunica. In this stage we also expect to add the [Core of the Hylar Reasoner](https://github.com/jeswr/hylar-core), as an actor.

This will be done in the [Comunica Feature Reasoning](https://github.com/comunica/comunica-feature-reasoning) repository.



## Stage 2 - Adaption of existing reasoners (15/9/2021-30/11/2021)

*Note: This stage is expected to only take ~1 week of full time work, however, 



## Stage 3

Full Project Proposal



