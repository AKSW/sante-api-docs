---
layout: default
title: Compiling
nav_order: 2
---

# Compiling
{: .no_toc }

For compiling the code and proceeding to the next step like
- Creating an Index
- Running

and so-on.

We need to execute this command on the ```root directory```

```
mvn clean install
```

By running this command in the project's root directory (where the `pom.xml` file resides), it first cleans up any previously compiled files or resources by removing the `target/` directory (`clean`). Then, it compiles the source code, runs unit tests, packages the project (e.g., into a JAR or WAR), and installs the package into the local Maven repository (`install`). This process ensures a fresh build and makes the project available for other local projects that might depend on it. If desired, tests can be skipped by appending `-DskipTests` to the command.