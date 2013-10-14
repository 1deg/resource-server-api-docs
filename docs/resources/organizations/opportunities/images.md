# Resources

## Images on Opportunities

### Attributes

[See Image attributes here.](/docs/resources/organizations/images.md)

### Endpoints

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/images`

Returns a list of the images on a organization.

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/images`

Uploads an image to a organization. Only one image of the same dimensions can be uploaded for a given resource.

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/images/:id`

Deletes an image from a organization.

### Permissions

* Only the owner of the associated organization and admins can manage images.
