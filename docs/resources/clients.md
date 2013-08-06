# Resources

## Clients

### Attributes

Field        | Type        | Optional | Description              
-------------|-------------|----------|-------------------------
`id`         | `integer`   |          | The unique API client ID.
`name`       | `string`    |          | The name of the API client.
`is_admin`   | `boolean`   |          | Whether or not the API client is an admin.

### Endpoints

#### `GET clients`

Returns a list of API clients. Standard pagination parameters apply.

#### `POST clients`

Creates a new API client.

#### `GET clients/:id`

Returns a specific API client.

#### `PUT clients/:id`

Updates a specific API client.

#### `DELETE clients/:id`

Deletes a specific API client.

### Permissions

* Only admins can manage clients.
