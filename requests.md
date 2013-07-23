# Requests

## Basics

All calls are made to the base URL, along with the specific provider path:

    https://xxxxx.xxxx.org/v1/

## Required Parameter

All requests require an API key parameter `api_key`.

## Standard Parameters

Similar request types use the same standard parameters. E.g. Requests to list providers use the same filter paramters.

### Timestamps

All timestamps should be in ISO 8601 format:

    YYYY-MM-DDTHH:mm:ss

### List parameters

| Parameter    | Type      | Description                    |
|--------------|-----------|--------------------------------|
| `page`       | `integer` | The offset.                    |
| `page_count` | `integer` | The number of items to return. |
| `order`      | `string`  | The sort order by which items will be returned. Common values are `name_asc` and `name_desc`. Defaults to `name_asc`.|
| `query`      | `string`  | The basic expression to query in the name field. |
