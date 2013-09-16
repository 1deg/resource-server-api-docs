# Resources

## Images on Opportunities

### Attributes

[See Image attributes here.](/docs/resources/providers/images.md)

### Endpoints

#### `GET resources/:resource_id/opportunities/:opportunity_id/images`

Returns a list of the images on a provider.

#### `POST resources/:resource_id/opportunities/:opportunity_id/images`

Uploads an image to a resource provider. Only one image of the same dimensions can be uploaded for a given resource.

#### `DELETE resources/:resource_id/opportunities/:opportunity_id/images/:id`

Deletes an image from a provider.

### Permissions

* Only the owner of the associated resource provider and admins can manage images.
