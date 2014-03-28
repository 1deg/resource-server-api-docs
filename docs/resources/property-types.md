## Resources

# Property Types

### Attributes

Field        | Type      | Note       | Description                        
-------------|-----------|------------|----------------------------------------
`id`         | `integer` | read-only  | The unique ID of the property type.
`name`       | `string`  | required   | The name of the property type.
`value_type` | `string`  | required   | The type of the property value (`string`, `integer`, or `decimal`)

### Endpoints

#### `GET /v1/property_types`

Returns all property types.

#### `POST /v1/property_types`

Creates a new property type.

#### `PUT /v1/property_types/:id`

Updates a property type.

#### `DELETE /v1/property_types/:id`

Deletes a specific property type.

### Permissions

* Only admins can manage property types.