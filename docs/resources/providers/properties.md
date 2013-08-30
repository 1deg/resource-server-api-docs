# Resources

## Properties on Resource Providers

### Attributes

Field           | Type     | Optional | Description                        
----------------|----------|----------|-----------------------------------
`name`          | `string` |          | The name of the property.          
`value_type`    | `string` |          | The value type of the property.    
`value`         | `string` |          | The value of the property.         

### Endpoints

#### `GET resources/:resource_id/properties`

Returns a list of the properties of a provider.

#### `POST resources/:resource_id/properties`

Adds a property to a provider.

#### `PUT resources/:resource_id/properties/:id`

Updates the value of a property. The `:id` in this case is the `name` attribute, but the parameter name is `id`

#### `DELETE resources/:resource_id/properties/:id`

Deletes a property from a provider. The `:id` in this case is the `name` attribute, but the parameter name is `id`

### Permissions

* Only resource owners and admins can manage properties.