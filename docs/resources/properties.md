## Resources

# Properties

### Attributes

Field           | Type     | Note     | Description                        
----------------|----------|----------|-----------------------------------
`name`          | `string` | required | The name of the property.          
`value_type`    | `string` | required | The value type of the property.    
`value`         | `string` | required | The value of the property.         

### Endpoints on Organizations

#### `GET /v1/organizations/:organization_id/properties`

Returns a list of the properties of an organization.

#### `POST /v1/organizations/:organization_id/properties`

Adds a property to an organization.

#### `PUT /v1/organizations/:organization_id/properties/:id`

Updates the value of a property. The `:id` in this case is the `name` attribute, but the parameter name is `id`. For example `/v1/organizations/3/properties/lang-spanish`.

#### `DELETE /v1/organizations/:organization_id/properties/:id`

Deletes a property from an organization. The `:id` in this case is the `name` attribute, but the parameter name is `id`, For example `/v1/organizations/3/properties/lang-spanish`.

### Endpoints on Opportunities

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/properties`

Returns a list of the properties of an opportunity.

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/properties`

Adds a property to an opportunity.

#### `PUT /v1/organizations/:organization_id/opportunities/:opportunity_id/properties/:id`

Updates the value of a property. The `:id` in this case is the `name` attribute, but the parameter name is `id`. For example `/v1/organizations/3/opportunities/5/properties/lang-spanish`.

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/properties/:id`

Deletes a property from an opportunity. The `:id` in this case is the `name` attribute, but the parameter name is `id`, For example `/v1/organizations/3/opportunities/5/properties/lang-spanish`.

### Permissions

* Only resource owners and admins can manage properties.
