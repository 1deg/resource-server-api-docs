# Requests

## Base URL

All calls are made to the base URL, along with the specific provider path:

    https://xxxxx.xxxx.org/v1/

## Required Parameter

All requests require an API key parameter `api_key`.

## Request Signatures

All requests with the `POST`, `PUT`, or `DELETE` HTTP verbs must include two additional headers in the request: `1deg-Date` and `1deg-Signature`.

### `1deg-Date`

This is a timestamp in ISO 8601 format at UTC. Requests that are received more or fewer than 60 seconds from the time specified in this header will be rejected.

Example header:

    1deg-Date: 2013-08-02T00:06:54Z

### `1deg-Signature`

This is the request signature that authenticates the sender. [Learn about how to build this request signature here.](request-signatures.md)

## Standard Parameters

Similar request types use the same standard parameters. E.g. Requests to list providers use the same filter paramters.

### Timestamps

All timestamps should be in ISO 8601 format:

    YYYY-MM-DDTHH:mm:ss

### Pagination parameters

 Parameter    | Type      | Description                    
--------------|-----------|--------------------------------
 `page`       | `integer` | The offset.                    
 `per_page`   | `integer` | The number of items to return. 
 `order`      | `string`  | The sort order by which items will be returned. Common values are `name_asc` and `name_desc`. Defaults to `name_asc`.
