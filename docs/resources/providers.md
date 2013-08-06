# Resources

## Resource Providers ("Resources")

### Attributes

Field          | Type         | Optional | Description                                  
---------------|--------------|----------|---------------------------------------
`id`           | `integer`    |          | Unique resource ID.
`name`         | `string`     |          | The name of the resource provider.
`website`      | `string`     | yes      | The URL of the resource provider's website.
`description`  | `text`       | yes      | The description of the resource provider.
`picture_path` | `string`     | yes      | URL of the resource's profile photo or logo.
`updated_at`   | `string`     | yes      | URL of the resource's profile photo or logo.

### Endpoints

#### `GET /v1/resources`

Returns a list of resource. Standard pagination parameters apply.

#### `POST /v1/resources`

Creates a new resource.

#### `GET /v1/resources/:id`

Returns a specific resource, along with the following nested objects:

- [`properties`](/docs/providers/properties.md)
- [`tags`](/docs/providers/tags.md)

#### `PUT /v1/resources/:id`

Updates a resource.

#### `DELETE /v1/resources/:id`

Deletes a resource.

### Permissions

* Anyone can add a new resource.
* Only admins and the original resource owner can update a resource.
* Only admins can delete a resource.
