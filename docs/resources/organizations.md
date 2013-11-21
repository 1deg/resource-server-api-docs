# Resources

## Organizations

### Attributes

Field          | Type         | Note     | Description                                  
---------------|--------------|----------|---------------------------------------
`id`           | `integer`    | auto     | Unique resource ID.
`name`         | `string`     | required | The name of the organization.
`website`      | `string`     |          | The URL of the organization's website.
`description`  | `text`       |          | The description of the organization.
`updated_at`   | `string`     |          | The timestamp of the last time the resource was updated.

### Endpoints

#### `GET /v1/organizations`

Returns a list of resource. Standard pagination parameters apply.

#### `POST /v1/organizations`

Creates a new resource.

#### `GET /v1/organizations/:id`

Returns a specific resource, along with the following nested objects:

- [`properties`](/docs/resources/organizations/properties.md)
- [`tags`](/docs/resources/organizations/tags.md)

#### `PUT /v1/organizations/:id`

Updates a resource.

#### `DELETE /v1/organizations/:id`

Deletes a resource.

### Permissions

* Anyone can add a new resource.
* Only admins and the original resource owner can update a resource.
* Only admins can delete a resource.
