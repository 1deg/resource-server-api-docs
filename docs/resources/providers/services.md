# Resources

## Services on Resource Providers

### Attributes

Field          | Type         | Optional | Description
---------------|--------------|-----------|----------------------------
`id`           | `integer`    |           | Unique service ID.
`title`        | `string`     |           | The name of the resource.
`is_primary`   | `boolean`    |           | Whether or not this is the resource's primary service.
`description`  | `text`       | yes       | The service's description.

### Endpoints

#### `GET resources/:resource_id/services`

Returns the list of services on a provider.

#### `POST resources/:resource_id/services`

Creates a new service on a provider.

#### `GET resources/:resource_id/serivces/:id`

Returns a specific service on a provider.

#### `PUT resources/:resource_id/serivces/:id`

Updates a service.

#### `DELETE resources/:resource_id/serivces/:id`

Deletes a service.
