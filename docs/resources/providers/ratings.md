# Resources

## Ratings on Resource Providers

### Attributes

Field            | Type      | Optional | Description                        
-----------------|-----------|----------|------------------------------------
`name`           | `string`  |          | The name of the rating.
`client_user_id` | `string`  |          | The ID of the user who provided this rating. This should be a unique identifier in the client's application.
`value`          | `string`  |          | The value of the rating. Generally a number 1-5, but this is a string since a rating value may not be numerical.

### Endpoints

#### `GET resources/:resource_id/ratings`

Returns the aggregate ratings on a provider.

#### `POST resources/:resource_id/ratings`

Creates a new rating.

#### `PUT resources/:resource_id/ratings/:id`

Updates a rating. The `:id` in this case is the `name` attribute, but the parameter name is `id`

#### `DELETE resources/:resource_id/ratings/:id`

Deletes a specific rating. The `:id` in this case is the `name` attribute, but the parameter name is `id`

### Permissions

* Anyone can add a rating on a resource.
* Only admins and the API client that submitted the original rating can update or delete it.