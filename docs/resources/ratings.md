## Resources

# Ratings

### Attributes

Field            | Type      | Note     | Description                        
-----------------|-----------|----------|------------------------------------
`name`           | `string`  | required | The name of the rating.
`client_user_id` | `string`  | required | The ID of the user who provided this rating. This should be a unique identifier in the client's application. This can only be set upon creation.
`value`          | `string`  | required | The value of the rating. Generally a number 1-5, but this is a string since a rating value may not be numerical.

### Endpoints on Organizations

#### `GET /v1/organizations/:organization_id/ratings`

Returns the aggregate ratings on an organization as an object. Example:

    {
      "Overall": 5
    }

#### `POST /v1/organizations/:organization_id/ratings`

Creates a new rating.

#### `PUT /v1/organizations/:organization_id/ratings/:id`

Updates a rating. The `:id` in this case is the `name` attribute, but the parameter name is `id`. For example `/v1/organizations/1/ratings/overall`.

#### `DELETE /v1/organizations/:organization_id/ratings/:id`

Deletes a specific rating. The `:id` in this case is the `name` attribute, but the parameter name is `id`. For example `/v1/organizations/1/ratings/overall`.

### Endpoints on Opportunities

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/ratings`

Returns the aggregate ratings on an opportunity as an object. Example:

    {
      "Overall": 5
    }

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/ratings`

Creates a new rating.

#### `PUT /v1/organizations/:organization_id/opportunities/:opportunity_id/ratings/:id`

Updates a rating. The `:id` in this case is the `name` attribute, but the parameter name is `id`. For example `/v1/organizations/1/opportunities/3/ratings/overall`.

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/ratings/:id`

Deletes a specific rating. The `:id` in this case is the `name` attribute, but the parameter name is `id`. For example `/v1/organizations/1/opportunities/3/ratings/overall`.

### Permissions

* Anyone can add a rating to a resource.
* Only admins and the API client that submitted the original rating can update or delete it.