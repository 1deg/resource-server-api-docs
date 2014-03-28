## Resources

# Rating Types

### Attributes

Field        | Type      | Note       | Description                        
-------------|-----------|------------|----------------------------------------
`id`         | `integer` | read-only  | The unique ID of the rating type.
`name`       | `string`  | required   | The name of the rating type.
`value_type` | `string`  | required   | The type of the rating value (`string`, `integer`, or `decimal`)

### Endpoints

#### `GET /v1/rating_types`

Returns all rating types.

#### `POST /v1/rating_types`

Creates a new rating type.

#### `PUT /v1/rating_types/:id`

Updates a rating type.

#### `DELETE /v1/rating_types/:id`

Deletes a specific rating type.

### Permissions

* Only admins can manage rating types.