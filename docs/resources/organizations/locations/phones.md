# Resources

## Phones on Locations

### Attributes

Field           | Type         | Note     | Description                           
----------------|--------------|----------|------------------------------------
`id`            | `integer`    | auto     | The unique ID of the phone number.
`digits`        | `string`     | required | The phone number.
`phone_type`    | `string`     |          | The type of phone number such as `fax` or `main`.
`is_primary`    | `boolean`    |          | Whether or not this is the location's primary phone number. Defaults to `false`, unless this is the only phone number.


### Endpoints

#### `GET resources/:resource_id/locations/:id/phones`

Returns all phone numbers on a location.

#### `POST resources/:resource_id/locations/:location_id/phones`

Creates a phone number on a location.

#### `PUT resources/:resource_id/locations/:location_id/phones/:id`

Updates a location's phone number.

#### `DELETE resources/:resource_id/locations/:location_id/phones/:id`

Deletes a location's phone number.