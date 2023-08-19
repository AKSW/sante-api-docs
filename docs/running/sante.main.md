---
title: Sante Main
layout: default
parent: Running
nav_order: 1
---

# Running SANTE MAIN Using Docker
{: .no_toc }

### Build SANTê Main :

```
docker build -t sante/main -f sante.main/Dockerfile .
```

### Run SANTê Main on the same Host Network and pass the Environment Variable ```endpoint``` which is exposed by KBox. It accesses the persistent volume ```index``` to store the required changes.

```
docker run --network=host -v index:/sante/foaf_kg -e endpoint=http://localhost:8080/kbox/query sante/main
```


# Running SANTE MAIN Using Jar
{: .no_toc }

Assuming that you successfully executed the KBox,

```
java -jar sante-main-*.jar index -endpoint http://localhost:8080/kbox/query -path \foaf_kg
```


#### Example
{: .no_toc }

```
java -jar sante.main-0.0.21-SNAPSHOT-jar-with-dependencies.jar index -endpoint http://localhost:8080/kbox/query -path ../../foaf_kg
```

