# Resources

## Rating Types

### Attributes

Field        | Type      | Optional | Description                        
-------------|-----------|----------|----------------------------------------
`id`         | `integer` |          | The unique ID of the rating type.
`name`       | `string`  |          | The name of the rating type.
`value_type` | `string`  |          | The type of the rating value (`string`, `integer`, or `decimal`)

### Endpoints

#### `GET rating_types`

Returns all rating types.

#### `POST rating_types`

Creates a new rating type.

#### `PUT rating_types/:id`

Updates a rating type.

#### `DELETE rating_types/:id`

Deletes a specific rating type.

### Permissions

* Only admins can manage rating types.