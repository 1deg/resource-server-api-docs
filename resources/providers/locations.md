# Resources

## Locations on Providers

### `GET providers/:id/locations`

Returns the location 

### `POST providers/:id/locations`

### `GET providers/:id/locations/:location_id`

Returns a specific location with the following nested resources:

- `phones`
- `schedule`

### `PUT providers/:id/locations/:location_id`

### `DELETE providers/:id/locations/:location_id`

### `POST providers/:id/locations/:location_id/phones`

Creates a phone number on a location.

### `PUT providers/:id/locations/:location_id/phones/:phone_id`

Updates a location's phone number.

### `DELETE providers/:id/locations/:location_id/phones/:phone_id`

Deletes a location's phone number.

### `POST providers/:id/locations/:location_id/schedule`

Creates a schedule on a location. Only one schedule can exist for a location. Attempting to create a new schedule for a location that already has one will result in a `401` error.

### `PUT providers/:id/locations/:location_id/schedule`

Updates a location's schedule.

### `DELETE providers/:id/locations/:location_id/schedule`

Deletes