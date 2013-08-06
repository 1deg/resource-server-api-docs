# Resources

## Comments on Providers

### Attributes

Field            | Type      | Optional | Description                        
-----------------|-----------|----------|------------------------------------
`content`        | `text`    |          | The content text of the body. This should be plain text and should not contain any HTML or other markup.
`client_user_id` | `string`  |          | The ID of the user who made this comment. This should be a unique identifier in the client's application.
`response_to_id` | `integer` | yes      | If this comment is in response to another comment, this should be the ID of that original comment.


### Endpoints

#### `GET providers/:resource_id/comments`

Returns the list of comments on a provider.

#### `POST providers/:resource_id/comments`

Creates a new comment on a resource.

#### `PUT providers/:resource_id/comments/:id`

Updates a comment.

#### `DELETE providers/:resource_id/comments/:id`

Deletes a comment.

### Permissions

* Anyone can add a comment on a resource.
* Only admins and the API client that submitted the original comment can update or delete it.