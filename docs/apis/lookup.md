---
title: Lookup
layout: default
parent: APIs
nav_order: 5
---

# Lookup API
{: .no_toc }


`GET /api/dbpedia-lookup`

*Retrieve entities in the format of DBpedia-Lookup*

DBpedia Lookup provides a way of searching through RDF data using natural language search queries. A user can therefore search for resources without having to use or learn SPARQL. This endpoint provides a way to use SANTé in accordance with DBpedia Lookup.

<h3 id="lookupdbpedia-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|maxResults|query|integer(int32)|true|Limit the amount of results|
|query|query|string|false|The natural language search query. Can be left empty, which will return all results.|
|minRelevance|query|number(double)|false|Set the relevance score a document must have to be considered as a result. Can be left empty, which will consider all scores.|

> Example responses

> 200 Response

```json
{
  "docs": [
    {
      "score": [
        "string"
      ],
      "refCount": [
        "string"
      ],
      "resource": [
        "string"
      ],
      "typeName": [
        "string"
      ],
      "comment": [
        "string"
      ],
      "label": [
        "string"
      ],
      "type": [
        "string"
      ],
      "category": [
        "string"
      ]
    }
  ]
}
```

<h3 id="lookupdbpedia-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The query was successful and returned a result.|[DbpediaDocumentCollection](#schemadbpediadocumentcollection)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request contains invalid input.|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|There was an issue while processing the query.|None|

<h3 id="lookupdbpedia-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>