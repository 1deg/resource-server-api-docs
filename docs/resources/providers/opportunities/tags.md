# Resources

## Tags on Opportunities

### Attributes

[See Tag attributes here.](/docs/resources/providers/tags.md)

### Endpoints

#### `GET resources/:resource_id/opportunities/:opportunity_id/tags`

Returns a list of the tags on an opportunity.

#### `POST resources/:resource_id/opportunities/:opportunity_id/tags`

Adds a tag to an opportunity. Anyone can add a tag.

#### `DELETE resources/:resource_id/opportunities/:opportunity_id/tags/:id`

Deletes a tag from an opportunity. The `:id` in this case is the `name` attribute, but the parameter name is `id`

### Permissions

* Anyone can add a tag.
* Only the owner of the associated resource provider and admins can delete a tag.
