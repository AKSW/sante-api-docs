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

## Getting started


### Quick start: Use as a GitHub Pages remote theme

Browse the sections below to navigate through the documentation:

[Docker Guide]({{ site.baseurl }}{% link docs/creating-an-index/Docker.md %})




1. Add Just the Docs to your Jekyll site's `_config.yml` as a [remote theme](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/)

```yaml
remote_theme: just-the-docs/just-the-docs
```

<small>You must have GitHub Pages enabled on your repo, one or more Markdown files, and a `_config.yml` file. [See an example repository](https://github.com/pmarsceill/jtd-remote)</small>

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
email, or any other method with the owners of this repository before making a change. Read more about becoming a contributor in [our GitHub repo](https://github.com/AKSW/sante-api-docs).

#### Thank you to the contributors of Just the Docs!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>