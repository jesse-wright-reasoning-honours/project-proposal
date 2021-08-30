# Scalable RDF Reasoning on the Web - Jesse Wright Honours Proposal

Reasoning is an ongoing challenge in IOT. From a theoretical perspective, existing reasoning techniques lack scalability; with traditional rule-based inferencing having a computational complexity ranging from polynomial time (e.g. OWL2RL) to exponential time (e.g. OWL2 Direct semantics). From an implementation perspective, few reasoners are written in languages such as Javascript which can be run in the browser; limiting the extent to which web clients can perform reasoning.

In this project we address these hurdles 


inference rules lack scalability - 

 such as OWL2RL and RDFS have lack scalability





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

*NOTE: Deadlines in this document are a an internal guideline and should not be treated as a date at which deliverables can be expected*

*NOTE: The priority of stages below may change depending on requirements/data availability of use-case partners*

## Stage 1 - Interface Development (-15/9/2021)

Interface development - develop a generic bus interface for Reasoners on Comunica. In this stage we also expect to add the [Core of the Hylar Reasoner](https://github.com/jeswr/hylar-core), as an actor.

This will be done in the [Comunica Feature Reasoning](https://github.com/comunica/comunica-feature-reasoning) repository.

## Stage 2 - Adaption of existing reasoners (15/9/2021-30/11/2021)

*Note: This stage is expected to only take ~1 week of full time work, however, coursework, teaching and work will be my primary focus' during this period*

Many OWL reasoners have been developed, most of which have been implemented in JAVA. These include ELK, HermiT, JFact3, Konclude, Openllet4, and Pellet. In this stage of our work we plan to use [JSweet](https://github.com/cincheo/jsweet) to transpile these reasoning engines into Typescript.
From there we shall manually update each codebase to comply with the rdf-js standard.

## Stage 3 - Development of a Lazy Reasoner (30/11/2021-15/12/2021)

To the best of our knowledge, there are no reasoners that currently perform *Lazy* reasoning, by inferring only those facts required to answer a given [SPARQL1.1 Query](https://www.w3.org/TR/sparql11-query/). In this stage of our work we intend to adapt the [Core of the Hylar Reasoner](https://github.com/jeswr/hylar-core) to perform lazy reasoning and create a lazy reasoning actor that can be configured with Comunica.

## Stage 4 - Development of Scalable Reasoning Techniques (16/12/2021-15/1/2022)



## Stage 5 - Development of Noise Resistant Reasoning Techniques (15/1/2022-15/2/2022)

## Stage 6 - Benchmarking (15/2/2022-30/2/2022)

Perform Benchmarks on 

Whilst the metrics we use may be subject to change the f

 - Evaluation of

## Stage 7 - Writing Thesis (30/2/2022-15/3/2022)

Completion of honours work, write these summarising experiments and results. Note the deadline won't be until the (6/22)

## Other Possible Reasearch Directions

### Performance Improvements
 - Implement reasoners in `C++` and use [`C++` addons](https://nodejs.org/api/addons.html) to invoke these engines from inside a comunica actor.

### Modularisation of Reasoners
 - For all of the reasoners developed throughout our work (both existing and novel), identify core compoenents (e.g.  Rule Parsing, Rule Filtering, Rule Ordering, Rule Evaluation etc.) and enable custom wiring of these components using an Actor-Bus model with [Components.js](https://componentsjs.readthedocs.io/en/latest/).

### Beyond OWL2Reasoning
 - Implement [stream reasoning](http://streamreasoning.org/slides/2016/10/rsp2016_01_rsp-introduction.pdf) and reasoning on time series data.
 - Implement [RDF*](https://w3c.github.io/rdf-star/cg-spec/editors_draft.html) Reasoning - we note that such features are blocked [until RDF* is supported by Comunica](https://github.com/comunica/comunica/issues/594).
