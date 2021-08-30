# Scalable RDF Reasoning on the Web 
## Jesse Wright Honours Project

🌱 This is an evolving document - which will be updated to reflect our progress over the course of the project.  🌱

### Background

Reasoning is an ongoing challenge in IOT. From a theoretical perspective, existing reasoning techniques lack scalability; with traditional rule-based inferencing having a computational complexity ranging from polynomial time (e.g. OWL2RL) to exponential time (e.g. OWL2 Direct semantics). From an implementation perspective, few reasoners are written in languages such as Javascript which can be run in the browser; limiting the extent to which web clients can perform reasoning.

In this project we shall address these hurdles by implementing and benchmarking a suite of RDF reasoners in [TypeScript](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html). These reasoners will be [rdf-js](https://rdf.js.org/) compliant, and will all have an interface that conforms the the [reasoning bus](https://github.com/comunica/comunica-feature-reasoning) for the [Comunica Engine](https://github.com/comunica/comunica). Moreover, the reasoners we intend to develop - will range from traditional reasoners, to those which use Machine Learning and heuristics to decrease computational complexity of reasoning at the cost of imperfect rule evaluation. 

The [Comunica Engine](https://github.com/comunica/comunica) is a "is a meta query engine using which query engines can be created. It does this by providing a set of modules that can be wired together in a flexible manner." (cf. [Comunica](https://comunica.dev/about/)). Comunica has built in [benchmarking](https://github.com/comunica/comunica#benchmarking) support. Comunica is seeing a growing adoption within the Semantic Web community, with usage in notable projects including the [solid community server](https://github.com/solid/community-server/blob/main/package.json).

### Related work

In recent years, there has been increasing investigation into RDF reasoners which do not use static inferencing techniques. Notable publications in this area include [Explainable Deep RDFS reasoner](https://arxiv.org/pdf/2002.03514.pdf), [Large Scale Incremental OWL/RDFS Reasoning over Fuzzy RDF Data](https://ieeexplore-ieee-org.virtual.anu.edu.au/stamp/stamp.jsp?tp=&arnumber=7881709) and [Deep Learning for noise-tolerant RDFS reasoning](http://www.semantic-web-journal.net/system/files/swj2186.pdf) which use novel techniques to embed components of RDF graphs in a vector format which can then be applied to a Deep Learning architecture. However, we observe that research focus is in handling noisy data rather than developing efficient reasoning algorithms.

The JS/TS only reasoner which we are aware of is the [Hylar Reasoner](https://github.com/ucbl/HyLAR-Reasoner), which we have transformed into a [lightweight package](https://github.com/jeswr/hylar-core).

There is a sizeable amount of literature dedicated to the benchmarking of RDF reasoners. As a result, many benchmarks have been developed - these include [OWL2Bench](https://link.springer.com/content/pdf/10.1007%2F978-3-030-62466-8.pdf) which aims to test coverage of OWL2 Language Constructs and [JustBench](https://link.springer.com/chapter/10.1007%2F978-3-642-17746-0_3) which is designed to evaluate the speed of reasoners on fixed-size datasets. In addition, competitions such as [ORE](https://link.springer.com/chapter/10.1007%2F978-3-319-46547-0_17) promote then benchmarking of reasoners against an array of metrics.

### Project Outline

*NOTE: Deadlines in this document are a an internal guideline and should not be treated as a date at which deliverables can be expected*

*NOTE: The priority of stages below may change depending on requirements/data availability of use-case partners*

#### Stage 1 - Interface Development (30/8/2021-15/9/2021)

Interface development - develop a generic bus interface for Reasoners on Comunica. In this stage we also expect to add the [Core of the Hylar Reasoner](https://github.com/jeswr/hylar-core), as an actor.

This will be done in the [Comunica Feature Reasoning](https://github.com/comunica/comunica-feature-reasoning) repository.

#### Stage 2 - Adaption of existing reasoners (15/9/2021-30/11/2021)

*Note: This stage is expected to only take ~1 week of full time work, however, coursework, teaching and work will be my primary focus' during this period*

Many OWL reasoners have been developed, most of which have been implemented in JAVA. These include ELK, HermiT, JFact3, Konclude, Openllet4, and Pellet. In this stage of our work we plan to use [JSweet](https://github.com/cincheo/jsweet) to transpile these reasoning engines into TypeScript.
From there we shall manually update each codebase to comply with the [rdf-js](https://rdf.js.org/) standard. Finally we will create a wrapper for each engine so that they can be used as a [reasoning actor](https://github.com/comunica/comunica-feature-reasoning) in Comunica.

#### Stage 3 - Development of a Lazy Reasoner (30/11/2021-15/12/2021)

To the best of our knowledge, there are no reasoners that currently perform *Lazy* reasoning, by inferring only those facts required to answer a given [SPARQL1.1 Query](https://www.w3.org/TR/sparql11-query/). In this stage of our work we intend to adapt the [core of the Hylar Reasoner](https://github.com/jeswr/hylar-core) to perform lazy reasoning and create a lazy reasoning actor that can be configured with Comunica.

#### Stage 4 - Development of Scalable Reasoning Techniques (16/12/2021-15/1/2022)

In this phase of our work, we intend to take the key lessons learned from recent publications such as [Explainable Deep RDFS reasoner](https://arxiv.org/pdf/2002.03514.pdf), [Large Scale Incremental OWL/RDFS Reasoning over Fuzzy RDF Data](https://ieeexplore-ieee-org.virtual.anu.edu.au/stamp/stamp.jsp?tp=&arnumber=7881709) and [Deep Learning for noise-tolerant RDFS reasoning](http://www.semantic-web-journal.net/system/files/swj2186.pdf). Using this, we shall develop novel JS/TS reasoners which use a range of static, heuristic based, and machine learning techniques to evaluate rules. We aim to implement reasoning with an linear (or better) time complexity.

#### Stage 5 - [OPTIONAL] Development of Noise Resistant Reasoning Techniques (15/1/2022-15/2/2022)

Similarly to stage 4, we intend to implement novel JS/TS reasoners, that are resistant to noisy datasets.

#### Stage 6 - [OPTIONAL] Development of Reasoning Techniques for streamed & timeseries data (15/1/2022-15/2/2022)

Similarly to stage 4, we intend to implement novel JS/TS reasoners, that work on streamed and timeseries' data.

#### Stage 7 - Benchmarking (15/2/2022-30/2/2022)

Perform benchmarking using existing benchmarks, and possibly new datasets provided by use-case partners.

The key metrics we will be focusing on are
 - Rule Evaluation Time/Computational Complexity
 - Rule Evaluation Accuracy

subject to the following changes in variables
 - Dataset Size
 - Rule Set (though at this stage we intent to primarily focus on RDFs rules)
 - Dataset Location (e.g. in-memory, file, online)
 - Dataset Distribution (i.e. federated across multiple Dataset Location(s))

and for the following purposes
 - Eager evaluation across the whole dataset
 - Lazily evaluating a subset of the data to fulfil a specific SPARQL query

#### Stage 7 - Writing Thesis (30/2/2022-15/3/2022)

Completion of honours work, write these summarising experiments and results. Note the official deadline will not be until the (6/22).

### Other Possible Reasearch Directions

#### Performance Improvements
 - Implement reasoners in `C++` and use [`C++` addons](https://nodejs.org/api/addons.html) to invoke these engines from inside a comunica actor.

#### Modularisation of Reasoners
 - For all of the reasoners developed throughout our work (both existing and novel), identify core compoenents (e.g.  Rule Parsing, Rule Filtering, Rule Ordering, Rule Evaluation etc.) and enable custom wiring of these components using an Actor-Mediator-Bus model with [Components.js](https://componentsjs.readthedocs.io/en/latest/).

#### Beyond OWL2Reasoning
 - Implement [stream reasoning](http://streamreasoning.org/slides/2016/10/rsp2016_01_rsp-introduction.pdf) and reasoning on time series data.
 - Implement [RDF\*](https://w3c.github.io/rdf-star/cg-spec/editors_draft.html) Reasoning - we note that such features are blocked [until RDF\* is supported by Comunica](https://github.com/comunica/comunica/issues/594).

<style>
.footer {
  display: !important none;
}
</style>
