---
title: Suggestion
layout: default
parent: APIs
nav_order: 1
---

# Suggestion API
{: .no_toc }

`POST /api/sante-suggest`

*Suggest entities using SANTé*

SANTé suggest provides a way to get a suggestion. It returns a list of possible suggestion results.

> Body parameter

```json
{
  "q": "string",
  "offset": 0,
  "limit": 1,
  "prefixes": [
    "string"
  ],
  "classes": [
    "string"
  ],
  "filters": [
    {}
  ],
  "content": [
    "string"
  ]
}
```

<h3 id="santesuggest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Query](#schemaquery)|true|none|

> Example responses

> 200 Response

```json
{
  "params": {
    "q": "string",
    "offset": 0,
    "limit": 1,
    "prefixes": [
      "string"
    ],
    "classes": [
      "string"
    ],
    "filters": [
      {}
    ],
    "content": [
      "string"
    ]
  },
  "result": [
    {
      "suggestion": "string",
      "score": "string"
    }
  ]
}
```

<h3 id="santesuggest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The query was successful and returned a result.|[SanteSuggestResponseDto](#schemasantesuggestresponsedto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request contains invalid input.|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|There was an issue while processing the query.|None|

<h3 id="santesuggest-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>
