# Resources

## Comments on Opportunities

### Attributes

[See Comment attributes here.](/docs/resources/providers/comments.md)

### Endpoints

#### `GET providers/:resource_id/opportunities/:opportunity_id/comments`

Returns the list of comments on an opportunity.

#### `POST providers/:resource_id/opportunities/:opportunity_id/comments`

Creates a new comment on an opportunity.

#### `PUT providers/:resource_id/opportunities/:opportunity_id/comments/:id`

Updates a comment.

#### `DELETE providers/:resource_id/opportunities/:opportunity_id/comments/:id`

Deletes a comment.

### Permissions

* Anyone can add a comment on an opportunity.
* Only admins and the API client that submitted the original comment can update or delete it.