# Resources

## Locations on Opportunities

### Attributes

[See Location attributes here.](/docs/resources/providers/locations.md)

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
