---
title: Jar
layout: default
parent: Creating an Index
nav_order: 2
---

# Creating Endpoint and Index using Jar from Source Code
{: .no_toc }

Before creating index, will help you to instantiate your first knowledge base search engine over FOAF ontology using KBox [https://github.com/AKSW/KBox](https://github.com/AKSW/KBox).

## 1) Download KBox and instantiate the FOAF knowledge graph.

Download the jar here [https://github.com/AKSW/KBox/releases](https://github.com/AKSW/KBox/releases)
and run the following command:

```
java -jar kbox-vXXXX.jar -server -kb "http://xmlns.com/foaf/0.1,https://www.w3.org/2000/01/rdf-schema,http://www.w3.org/2002/07/owl,http://www.w3.org/1999/02/22-rdf-syntax-ns,http://purl.org/dc/elements/1.1/,http://purl.org/dc/terms/,http://purl.org/dc/dcam/,http://purl.org/dc/dcmitype/" -install
Loading Model...
Publishing service on http://localhost:8080/kbox/query
Service up and running ;-) ...
```
You can now access and query your knowledge graph at [http://localhost:8080](http://localhost:8080).
Notice that in the example above, we also include RDFS, RDF, and OWL ontologies. That's because we need their information to correctly instantiate FOAF ontology.
If the SPARQL endpoint does not contain all necessary information, SANTé will not be capable of retrieving or searching for it and will display the resource as ```URI```.


## 2) Create the index

```
java -jar sante.main-*.jar index -endpoint <endpoint> -path <path>
```
where:

    <endpoint> stands for the SPARQL endpoint.
	 
    <path>     stands for the target index directory.


Then, [Build and Run SANTE MAIN]({% link docs/running/sante.main.md %}) to get the ```index``` directory.

