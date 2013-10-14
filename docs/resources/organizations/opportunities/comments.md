# Resources

## Comments on Opportunities

### Attributes

[See Comment attributes here.](/docs/resources/organizations/comments.md)

### Endpoints

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/comments`

Returns the list of comments on an opportunity.

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/comments`

Creates a new comment on an opportunity.

#### `PUT /v1/organizations/:organization_id/opportunities/:opportunity_id/comments/:id`

Updates a comment.

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/comments/:id`

Deletes a comment.

### Permissions

* Anyone can add a comment on an opportunity.
* Only admins and the API client that submitted the original comment can update or delete it.