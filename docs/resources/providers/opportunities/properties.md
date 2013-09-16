# Resources

## Properties on Opportunities

### Attributes

[See Property attributes here.](/docs/resources/providers/properties.md)

### Endpoints

#### `GET resources/:resource_id/opportunities/:opportunity_id/properties`

Returns a list of the properties of an opportunity.

#### `POST resources/:resource_id/opportunities/:opportunity_id/properties`

Adds a property to an opportunity.

#### `PUT resources/:resource_id/opportunities/:opportunity_id/properties/:id`

Updates the value of a property. The `:id` in this case is the `name` attribute, but the parameter name is `id`

#### `DELETE resources/:resource_id/opportunities/:opportunity_id/properties/:id`

Deletes a property from an opportunity. The `:id` in this case is the `name` attribute, but the parameter name is `id`

### Permissions

* Only resource owners and admins can manage properties.