# project-proposal

Reasoning is an ongoing challenge in IOT.

# Existing work
## (RDF Reasoning on Large Ontologies: A Study on Cultural Heritage and Wikidata)[https://ieeexplore.ieee.org/abstract/document/7881709]

## (Explainable Deep RDFS reasoner)[https://arxiv.org/pdf/2002.03514.pdf]

## (Deep Learning for noise-tolerant RDFS reasoning)[http://www.semantic-web-journal.net/system/files/swj2186.pdf]

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

Full Project Proposal



