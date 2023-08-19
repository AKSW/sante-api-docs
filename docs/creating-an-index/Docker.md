---
title: Docker
layout: default
parent: Creating an Index
nav_order: 1
---


# Creating Endpoint and Index using Docker
{: .no_toc }


1) Run Kbox docker image on Host Network (which is pulled from DockerHub automatically)

```
docker run --network=host aksw/kbox -server -kb "http://xmlns.com/foaf/0.1,https://www.w3.org/2000/01/rdf-schema,http://www.w3.org/2002/07/owl,http://www.w3.org/1999/02/22-rdf-syntax-ns,http://purl.org/dc/elements/1.1/,http://purl.org/dc/terms/,http://purl.org/dc/dcam/,http://purl.org/dc/dcmitype/" -install
```

2) Create a volume named ```index```. This will help to access the index folder from all the docker images we build in the process.

```
docker volume create index
```


Then, [Build and Run SANTE MAIN]({% link docs/running/sante.main.md %}) to get the ```index``` volume.


Finally, we can use ```index``` volume to run API and SMILE.



