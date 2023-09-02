---
layout: default
title: Known Issues and Limitation
nav_order: 6
---

# Known Issues and Limitation
{: .no_toc }

## Blank Nodes
{: .no_toc }

There many issues regarding RDF blank nodes such as no uniformity or standard way of tackling them.
To avoid custom implementations, we have made a design decision not to support blank nodes.
If your dataset happens to have blank nodes, you should perform a canonization using the query below (customizing it according to your needs).
This query will assign an URI with the prefix ```blanknode://``` to every blank node of your dataset.

```
DELETE {?s ?p ?o}
INSERT {?s ?p ?cO}
WHERE
{
     ?s ?p ?o.
     FILTER(isblank(?o))
     bind (iri(concat("blanknode://",SHA1(STR(iri(?o))))) as ?cO)
};

DELETE {?s ?p ?o}
INSERT {?cS ?p ?o}
WHERE
{
    ?s ?p ?o.
    FILTER(isblank(?s))
	bind (iri(concat("blanknode://",SHA1(STR(iri(?s))))) as ?cS)
};
```