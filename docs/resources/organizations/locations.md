# Resources

## Locations on Resource Providers

### Attributes

Field          | Type         | Note      | Description                         
---------------|--------------|-----------|------------------------------------
`id`           | `integer`    | auto      | Unique resource ID.
`name`         | `string`     | required  | The name of the location.
`address`      | `string`     |           | The location's street address website.
`unit`         | `string`     |           | The address unit, such as suite or level number.
`city`         | `string`     | required  | The location's city.
`state`        | `string`     | required  | The location's 2-letter state abbreviation.
`zip_code`     | `string`     |           | The location's USPS Zip code.
`lat`          | `float`      | auto      | The latitude of the location.
`long`         | `float`      | auto      | The longitude of the location.
`is_primary`   | `boolean`    |           | Whether or not this is the resource's primary location. Default is `false`, unless no other location exists.

### Endpoints

#### `GET /v1/organizations/:organization_id/locations`

Returns the locations of a resource.

#### `POST /v1/organizations/:organization_id/locations`

Creates a new location of a resource.

#### `GET /v1/organizations/:organization_id/locations/:id`

Returns a specific location with the following nested resources:

- [`phones`](locations/phones.md)
- [`schedule`](locations/schedule.md)

#### `PUT /v1/organizations/:organization_id/locations/:id`

Updates a location of a resource.

#### `DELETE /v1/organizations/:organization_id/locations/:id`

Deletes a location of a resource.

#### Permissions

* Only resource owners and admins can manage locations, schedules, and phone numbers.
