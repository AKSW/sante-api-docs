---
title: Resource
layout: default
parent: APIs
nav_order: 4
---

# Resource API
{: .no_toc }

`GET /api/resource`

*Perform a resource lookup given a URI.*

Starting from a URI, SANTé can be used to lookup a resource  and return a JSON-LD formatted result.

<h3 id="getresource-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uri|query|string|true|URI|

> Example responses

<h3 id="getresource-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The resource lookup was successful and returned a result.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|The request contains invalid input.|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|There was an issue while processing the query.|None|

<h3 id="getresource-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>
