---
title: Sante API
layout: default
parent: Running
nav_order: 3
---

# Running SANTE API Using Docker
{: .no_toc }


Make sure you have created the index in the project as instructed [here]({% link docs/creating-an-index/creating-an-index.md %}).

### Building the Docker Image:

```
docker build -t sante/api -f sante.api/Dockerfile .   
```

### To run the docker image along with the specified ```index```, here is the command:

```
docker run -p 8080:8080 -v index:/index -itd sante/api
```


# Running SANTE API Spring Boot Application Using Maven Commands
{: .no_toc }

SANTé also has a standalone Spring Boot API with five different endpoints.
This Spring Boot application can be run by changing into the `sante.api` directory and executing
```bash
$ mvn spring-boot:run -Dindex.path=YOUR_INDEX_PATH_GOES_HERE
```

Once the application is running, by default, the documentation (Swagger) for all the applications endpoints can be accessed via
```bash
http://localhost:8080/swagger
```
