# Responses

## Errors

Errors will be returned with a `status` and `error` message, as in the following example:

    HTTP/1.1 400 Bad Request
    Content-Type: application/json; charset=utf-8
    
    {
      "status": "error",
      "error": "Missing API key."
    }

## Response Codes

| HTTP Code | Name                  | Description                     |
|-----------|-----------------------|---------------------------------|
| 200       | OK                    | Everything's fine. A normal response. |
| 400       | Bad Request           | There was something wrong with the request, probably due to a missing API key. |
| 401       | Unauthorized          | The request could not be authorized, probably due to an invalid API key or signature. |
| 403       | Forbidden             | The request is not allowed. Likely the client with the given API key does not have access to perform the requested action.  |
| 404       | Not found             | There's nothing at the endpoint requested. |
| 500       | Internal Server Error | It's not your fault. There was a problem at the server with fulfilling the request. |