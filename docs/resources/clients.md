## Resources

# Clients

### Attributes

Field        | Type        | Note      | Description              
-------------|-------------|-----------|-------------------------
`id`         | `integer`   | read-only | The unique API client ID.
`name`       | `string`    | required  | The name of the API client.
`is_admin`   | `boolean`   |           | Whether or not the API client is an admin. Default is `false`.

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

#### `PUT clients/:id/password`

This sets the admin UI password for the client. A `password` parameter (`string`) is required, which is the unencrypted password.

#### `PUT clients/:id/authenticate`

This request returns whether or not the client is authenticated to use the admin UI. A `password` parameter (`string`) is required, which is the client's unencrypted password.

If the password matches the client ID, the response is:

    {
      "status": "OK",
      "message": "Client is authenticated."
    }

Otherwise, the response is:

    {
      "status": "bad",
      "message": "Client is not authenticated."
    }

### Permissions

* Only admins can manage clients.
