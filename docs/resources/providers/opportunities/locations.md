# Resources

## Locations on Opportunities

### Attributes

Field          | Type         | Optional | Description                         
---------------|--------------|-----------|------------------------------------
`id`           | `integer`    |           | Unique resource ID.
`name`         | `string`     |           | The name of the location.
`address`      | `string`     | yes       | The location's street address website.
`unit`         | `string`     | yes       | The address unit, such as suite or level number.
`city`         | `string`     |           | The location's city.
`state`        | `string`     |           | The location's 2-letter state abbreviation.
`zip_code`     | `string`     | yes       | The location's USPS Zip code.
`lat`          | `float`      | read-only | The latitude of the location.
`long`         | `float`      | read-only | The longitude of the location.
`is_primary`   | `boolean`    |           | Whether or not this is the resource's primary location.

### Endpoints

#### `GET resources/:resource_id/opportunities/:opportunity_id/locations`

Returns the locations of an opportunity.

#### `POST resources/:resource_id/opportunities/:opportunity_id/locations`

Creates a new location of an opportunity.

#### `GET resources/:resource_id/opportunities/:opportunity_id/locations/:id`

Returns a specific location with the following nested resources:

- [`phones`](locations/phones.md)
- [`schedule`](locations/schedule.md)

#### `PUT resources/:resource_id/opportunities/:opportunity_id/locations/:id`

Updates a location of an opportunity.

#### `DELETE resources/:resource_id/opportunities/:opportunity_id/locations/:id`

Deletes a location of an opportunity.

#### Permissions

* Only resource owners and admins can manage locations, schedules, and phone numbers.
