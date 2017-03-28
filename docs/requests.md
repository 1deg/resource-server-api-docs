# Requests

## Base URL

All calls are made to the base URL, along with the specific resource path:

    https://data.1degree.org/v1/

## Required Parameter

All requests require an API key parameter `api_key`.

## Common Parameters

Many requests share parameters. Most resource collections support [pagination parameters](/docs/common/pagination.md), and certain resource collections (`Organizations` and `Opportunities`) support [query parameters](/docs/common/query.md).

## Request Signatures

All requests with the `POST`, `PUT`, or `DELETE` HTTP verbs must include two additional headers in the request: `1deg-Date` and `1deg-Signature`.

### `1deg-Date`

This is a timestamp in ISO 8601 format at UTC. Requests that are received more or fewer than 60 seconds from the time specified in this header will be rejected.

Example header:

    1deg-Date: 2013-08-02T00:06:54Z

### `1deg-Signature`

This is the request signature that authenticates the sender. [Learn about how to build this request signature here.](request-signatures.md)

### Timestamps

All timestamps should be in ISO 8601 format at UTC:

    YYYY-MM-DDTHH:mm:ss
