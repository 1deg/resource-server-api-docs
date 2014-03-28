## Resources

# Comments

### Attributes

Field            | Type      | Note     | Description                        
-----------------|-----------|------------|------------------------------------
`id`             | `integer` | read-only  | The unique ID of the comment.
`client_id`      | `integer` | read-only  | The ID of the API client that added the comment.
`client_user_id` | `string`  | required   | The ID of the user who made this comment. This should be a unique identifier in the client's application.
`response_to_id` | `integer` |            | If this comment is in response to another comment, this should be the ID of that original comment. Can only be set upon creation (`POST`).
`content`        | `text`    | required   | The con-tent text of the body. This should be plain text and should not contain any HTML or other markup.
`responses`      | `Array<Comment>` | read-only | Any responses to this comment as an array of comments.

### Endpoints

#### `GET /v1/organizations/:organization_id/comments`

Returns the list of comments on an organization.

#### `POST /v1/organizations/:organization_id/comments`

Creates a new comment on an organization.

#### `PUT /v1/organizations/:organization_id/comments/:id`

Updates a comment.

#### `DELETE /v1/organizations/:organization_id/comments/:id`

Deletes a comment.

### Permissions

* Anyone can add a comment on an organization.
* Only admins and the API client that submitted the original comment can update or delete it.