---
title: Sante Smile
layout: default
parent: Running
nav_order: 2
---


# Running SANTE SMILE Using Docker
{: .no_toc }

**Fastest way to run SANTé is to build docker image using the given dockerfile**

Make sure you have created the index in the project as instructed [here]({% link docs/creating-an-index/creating-an-index.md %}).


### Building the Docker Image:

```
docker build -t sante/smile -f sante.smile/Dockerfile .   
```

### To run the docker image along with the specified ```index```, here is the command:

```
docker run -p 7070:7070 -v index:/index -itd sante/smile
```

After running the image, the application is exposed at ```http://localhost:7070```




# Running SANTE SMILE Using WAR
{: .no_toc }

First, compile the project as shown [here]({% link docs/compiling.md %}).

```
...\sante\mvn clean install
...
[INFO] Reactor Summary:
[INFO] 
[INFO] parent 0.0.21-SNAPSHOT ............................. SUCCESS [  0.105 s]
[INFO] sante.core 0.0.21-SNAPSHOT ......................... SUCCESS [  1.073 s]
[INFO] sante.smile.2 2.5.3 ................................ SUCCESS [  2.883 s]
[INFO] sante.main 0.0.21-SNAPSHOT ......................... SUCCESS [  6.563 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  10.747 s
[INFO] Finished at: 2023-06-26T16:58:03+05:30
[INFO] ------------------------------------------------------------------------
```
The smile WAR file will be generated at ```sante/sante.smile/target/sante.smile-2.5.3.war```


Then, run the specified WAR file along with the ```index``` directory path

```
java -jar -Dsante.index.path= <YOUR_INDEX_PATH_GOES_HERE> sante.smile-2.5.3.war
```

#### Example
{: .no_toc }

If the ```index``` folder is located in the root directory:

```
java -jar -Dsante.index.path=../../foaf_kg  sante.smile-2.5.3.war
```