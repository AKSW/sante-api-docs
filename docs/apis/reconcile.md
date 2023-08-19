---
title: Reconcile
layout: default
parent: APIs
nav_order: 3
---

# Reconcile API
{: .no_toc }


`GET /api/reconcile`

*Retrieve entities in accordance W3C Reconciliation*

Reconciliation provides a way of matching similar entities. ATTENTION: This GET endpoint is only supposed to be used for interactive debugging of reconciliation queries in a web browser.

<h3 id="batchreconcileget-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|queries|query|string|true|Query batch|

> Example responses

> 200 Response

```json
{
  "q1": {
    "result": [
      {
        "id": "string",
        "name": "string",
        "score": 0,
        "features": [
          {
            "id": "string",
            "value": "string"
          }
        ],
        "match": true
      }
    ]
  }
}
```

<h3 id="batchreconcileget-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The reconciliation was successful and returned a result.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request contains invalid input.|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|There was an issue while processing the query.|None|

<h3 id="batchreconcileget-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>



`POST /api/reconcile`

*Retrieve entities in the format of W3C Reconciliation*

Reconciliation provides a way of matching similar entities. SANTé is used in the background to facilitate the matching via a search query.

> Body parameter

```json
{
  "property1": {
    "query": "string",
    "type": [
      {
        "id": "string",
        "name": "string"
      }
    ],
    "limit": 1,
    "properties": [
      {
        "pid": "string",
        "v": "string"
      }
    ]
  },
  "property2": {
    "query": "string",
    "type": [
      {
        "id": "string",
        "name": "string"
      }
    ],
    "limit": 1,
    "properties": [
      {
        "pid": "string",
        "v": "string"
      }
    ]
  }
}
```

<h3 id="batchreconcilepost-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» **additionalProperties**|body|[ReconciliationQuery](#schemareconciliationquery)|false|none|
|»» query|body|string|true|none|
|»» type|body|[[ReconciliationType](#schemareconciliationtype)]|false|none|
|»»» id|body|string|true|none|
|»»» name|body|string|true|none|
|»» limit|body|integer(int32)|false|none|
|»» properties|body|[[ReconciliationProperty](#schemareconciliationproperty)]|false|none|
|»»» pid|body|string|true|none|
|»»» v|body|string|true|none|

> Example responses

> 200 Response

```json
{
  "q1": {
    "result": [
      {
        "id": "string",
        "name": "string",
        "score": 0,
        "features": [
          {
            "id": "string",
            "value": "string"
          }
        ],
        "match": true
      }
    ]
  }
}
```

<h3 id="batchreconcilepost-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The query was successful and returned a result.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request contains invalid input.|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|There was an issue while processing the request.|None|

<h3 id="batchreconcilepost-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>
