---
layout: default
title: Home
nav_order: 1
description: "SANTé stands for Semantic Search Engine and is designed to simplify RDF data access and exploration. SANTé covers different aspects of search engines, such as indexing, ranking as well as interaction. You can use SANTé via the command line or via SANTé Web Interface (smile)."
permalink: /
---

# Documentation
{: .fs-9 }

SANTé stands for Semantic Search Engine and is designed to simplify RDF data access and exploration. SANTé covers different aspects of search engines, such as indexing, ranking as well as interaction. You can use SANTé via the command line or via SANTé Web Interface (smile).
{: .fs-6 .fw-300 }

[Get started now](#getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View it on GitHub](https://github.com/aksw/sante){: .btn .fs-5 .mb-4 .mb-md-0 }

---

{: .new }
> **SANTé in Multilingual support is in development cycle!**
> See [the other Branch](https://github.com/aksw/sante/tree/mulang) for a detailed breakdown.

# SANTé in 5 minutes
{: .no_toc }


In this 5 minutes tutorial, we will help you to instantiate your first knowledge base search engine over FOAF ontology using KBox [https://github.com/AKSW/KBox](https://github.com/AKSW/KBox).

1) Download KBox and instantiate the FOAF knowledge graph.

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

2) Download one of the available SANTé runnable jar files.

Download the jar here [https://github.com/AKSW/sante/releases](https://github.com/AKSW/sante/releases)

3) Create the index.

Assuming that you successfully performed step 1,
```
java -jar sante-main-*.jar index -endpoint http://localhost:8080/kbox/query -path \foaf_kg
```

4) Download one of the available smile WAR files (same version as step 2).

Download the WAR here [https://github.com/AKSW/sante/releases](https://github.com/AKSW/sante/releases)

5) Instantiate smile
```
java -jar -Dsante.index.path=\foaf_kg sante.smile-*.war
 ____    _    _   _ _____  __   __        _______ ____       _
 / ___|  / \  | \ | |_   _|/_/_  \ \      / / ____| __ )     / \   _ __  _ __
 \___ \ / _ \ |  \| | | || ____|  \ \ /\ / /|  _| |  _ \    / _ \ | '_ \| '_ \
  ___) / ___ \| |\  | | ||  _|_    \ V  V / | |___| |_) |  / ___ \| |_) | |_) |
 |____/_/   \_\_| \_| |_||_____|    \_/\_/  |_____|____/  /_/   \_\ .__/| .__/
                                                                  |_|   |_|

2022-09-13 09:58:15.842  INFO 21938 --- [           main] org.aksw.sante.SanteWebApp               : Starting SanteWebApp v2.5.3 using Java 11.0.10 on ... with PID 21938
...
2022-09-13 09:58:15.846  INFO 21938 --- [           main] org.aksw.sante.SanteWebApp               : No active profile set, falling back to default profiles: default
```

If you correctly executed all the steps above, now you should be able to access SANTé at [http://localhost:9090](http://localhost:9090).


### Local installation: Use the gem-based theme

1. Install the Ruby Gem
  ```bash
  $ gem install just-the-docs
  ```
  ```yaml
  # .. or add it to your Jekyll site’s Gemfile
  gem "just-the-docs"
  ```

2. Add Just the Docs to your Jekyll site’s `_config.yml`
  ```yaml
  theme: "just-the-docs"
  ```

3. _Optional:_ Initialize search data (creates `search-data.json`)
  ```bash
  $ bundle exec just-the-docs rake search:init
  ```

3. Run your local Jekyll server
  ```bash
  $ jekyll serve
  ```
  ```bash
  # .. or if you're using a Gemfile (bundler)
  $ bundle exec jekyll serve
  ```


4. Point your web browser to [http://localhost:4000](http://localhost:4000)

If that doesn't work,

```
export PATH="$HOME/.gem/ruby/3.2.0/bin:$PATH"  
```

```
source ~/.zshrc       
```

```
bundle exec jekyll serve                                                                                     
```

If you're hosting your site on GitHub Pages, [set up GitHub Pages and Jekyll locally](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll) so that you can more easily work in your development environment.

### Configure Just the Docs

- [See configuration options]({{ site.baseurl }}{% link docs/configuration.md %})

---

## About the project

SANTé &copy; by [Edgard Marx](https://aksw.org/EdgardMarx).


### Contributing

When contributing to this repository, please first discuss the change you wish to make via issue,
email, or any other method with the owners of this repository before making a change. Read more about becoming a contributor in [docs](https://github.com/AKSW/sante-api-docs) or [our GitHub repo](https://github.com/AKSW/sante-api-docs).

#### Thank you to the contributors!