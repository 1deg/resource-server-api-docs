## Resources

# Tags

### Attributes

 Field  | Type     | Note     | Description                        
--------|----------|----------|------------------------------------
 `name` | `string` | required | The name of the tag.               

### Endpoints on Organizations

#### `GET /v1/organizations/:organization_id/tags`

Returns a list of the tags on a organization.

#### `POST /v1/organizations/:organization_id/tags`

Adds a tag to a organization. Anyone can add a tag to a resource.

#### `DELETE /v1/organizations/:organization_id/tags/:id`

Deletes a tag from an organization. The `:id` in this case is the human readable `name`, but the parameter name itself is `id`. For example `/organizations/3/tags/health`

### Endpoints on Opportunities

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/tags`

Returns a list of the tags on an opportunity.

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/tags`

Adds a tag to an opportunity. Anyone can add a tag to an opportunity.

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/tags/:id`

Deletes a tag from an opportunity. The `:id` in this case is the human readable `name`, but the parameter name itself is `id`. For example `/organizations/3/opportunities/4/tags/health`


### Permissions

* Anyone can add a tag.
* Only the owner of the associated resource and admins can delete a tag.
