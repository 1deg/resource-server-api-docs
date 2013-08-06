# Resources

## Tags on Resource Providers

### Attributes

 Field  | Type     | Optional | Description                        
--------|----------|----------|------------------------------------
 `name` | `string` |          | The name of the tag.               

### Endpoints

#### `GET resources/:resource_id/tags`

Returns a list of the tags on a provider.

#### `POST resources/:resource_id/tags`

Adds a tag to a provider. Anyone can add a tag to a resource.

#### `DELETE resources/:resource_id/tags/:id`

Deletes a tag from a provider. The `:id` in this case is the `name` attribute, but the parameter name is `id`

### Permissions

* Anyone can add a tag.
* Only the owner of the associated resource provider and admins can delete a tag.
