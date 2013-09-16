# Resources

## Property Types

### Attributes

Field        | Type      | Note     | Description                        
-------------|-----------|----------|----------------------------------------
`id`         | `integer` | auto     | The unique ID of the property type.
`name`       | `string`  | required | The name of the property type.
`value_type` | `string`  | required | The type of the property value (`string`, `integer`, or `decimal`)

### Endpoints

#### `GET property_types`

Returns all property types.

#### `POST property_types`

Creates a new property type.

#### `PUT property_types/:id`

Updates a property type.

#### `DELETE property_types/:id`

Deletes a specific property type.

### Permissions

* Only admins can manage property types.