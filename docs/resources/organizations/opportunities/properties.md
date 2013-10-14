# Resources

## Properties on Opportunities

### Attributes

[See Property attributes here.](/docs/resources/organizations/properties.md)

### Endpoints

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/properties`

Returns a list of the properties of an opportunity.

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/properties`

Adds a property to an opportunity.

#### `PUT /v1/organizations/:organization_id/opportunities/:opportunity_id/properties/:id`

Updates the value of a property. The `:id` in this case is the `name` attribute, but the parameter name is `id`

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/properties/:id`

Deletes a property from an opportunity. The `:id` in this case is the `name` attribute, but the parameter name is `id`

### Permissions

* Only resource owners and admins can manage properties.