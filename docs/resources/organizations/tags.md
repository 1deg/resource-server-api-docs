# Resources

## Tags on Resource Providers

### Attributes

 Field  | Type     | Note     | Description                        
--------|----------|----------|------------------------------------
 `name` | `string` | required | The name of the tag.               

### Endpoints

#### `GET /v1/organizations/:organization_id/tags`

Returns a list of the tags on a organization.

#### `POST /v1/organizations/:organization_id/tags`

Adds a tag to a organization. Anyone can add a tag to a resource.

#### `DELETE /v1/organizations/:organization_id/tags/:id`

Deletes a tag from a organization. The `:id` in this case is the `name` attribute, but the parameter name is `id`

### Permissions

* Anyone can add a tag.
* Only the owner of the associated organization and admins can delete a tag.
