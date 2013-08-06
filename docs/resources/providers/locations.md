# Resources

## Locations on Resource Providers

### Attributes

Field          | Type         | Optional | Description                         
---------------|--------------|-----------|------------------------------------
`id`           | `integer`    |           | Unique resource ID.
`name`         | `string`     |           | The name of the location.
`is_primary`   | `boolean`    |           | Whether or not this is the resource's primary location.
`address`      | `string`     | yes       | The location's street address website.
`unit`         | `string`     | yes       | The address unit, such as suite or level number.
`city`         | `string`     |           | The location's city.
`state`        | `string`     |           | The location's 2-letter state abbreviation.
`zip_code`     | `string`     | yes       | The location's USPS Zip code.
`lat`          | `float`      | read-only | The latitude of the location.
`long`         | `float`      | read-only | The longitude of the location.

### Endpoints

#### `GET resources/:resource_id/locations`

Returns a location.

#### `POST resources/:resource_id/locations`

#### `GET resources/:resource_id/locations/:id`

Returns a specific location with the following nested resources:

- `phones`
- `schedule`

#### `PUT resources/:resource_id/locations/:id`

#### `DELETE resources/:resource_id/locations/:id`

#### Permissions

* Only resource owners and admins can manage locations, schedules, and phone numbers.

## Phones on Locations

### Attributes

Field           | Type         | Optional | Description                           
----------------|--------------|----------|------------------------------------
`id`            | `integer`    |          | The unique ID of the phone number.
`digits`        | `string`     |          | The phone number.
`phone_type`    | `string`     | yes      | The type of phone number such as `fax` or `main`.
`is_primary`    | `boolean`    |          | Whether or not this is the location's primary phone number.


### Endpoints

#### `GET resources/:resource_id/locations/:id/phones`

Returns all phone numbers on a location.

#### `POST resources/:resource_id/locations/:location_id/phones`

Creates a phone number on a location.

#### `PUT resources/:resource_id/locations/:location_id/phones/:id`

Updates a location's phone number.

#### `DELETE resources/:resource_id/locations/:location_id/phones/:id`

Deletes a location's phone number.

## Schedules on Locations

### Attributes

Field             | Type         | Optional | Description    
------------------|--------------|----------|---------------------------------
`monday_start`    | `string`     | yes      | The Monday opening hour of the location.
`monday_end`      | `string`     | yes      | The Monday closing hour of the location.
`tuesday_start`   | `string`     | yes      | The Monday opening hour of the location.
`tuesday_end`     | `string`     | yes      | The Monday closing hour of the location.
`wednesday_start` | `string`     | yes      | The Monday opening hour of the location.
`wednesday_end`   | `string`     | yes      | The Monday closing hour of the location.
`thursday_start`  | `string`     | yes      | The Monday opening hour of the location.
`thursday_end`    | `string`     | yes      | The Monday closing hour of the location.
`friday_start`    | `string`     | yes      | The Monday opening hour of the location.
`friday_end`      | `string`     | yes      | The Monday closing hour of the location.
`saturday_start`  | `string`     | yes      | The Monday opening hour of the location.
`saturday_end`    | `string`     | yes      | The Monday closing hour of the location.
`sunday_start`    | `string`     | yes      | The Monday opening hour of the location.
`sunday_end`      | `string`     | yes      | The Monday closing hour of the location.
`notes`           | `text`       | yes      | The Monday opening hour of the location.

All hours `string` fields are of the format:

    HH:mm

### Endpoints

#### `POST resources/:resource_id/locations/:id/schedule`

Creates a schedule on a location. Only one schedule can exist for a location.

#### `PUT resources/:resource_id/locations/:id/schedule`

Updates a location's schedule.

#### `DELETE resources/:resource_id/locations/:id/schedule`

Deletes the location's schedule.
