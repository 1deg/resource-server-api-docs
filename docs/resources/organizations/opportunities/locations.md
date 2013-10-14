# Resources

## Locations on Opportunities

### Attributes

[See Location attributes here.](/docs/resources/organizations/locations.md)

### Endpoints

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/locations`

Returns the locations of an opportunity.

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/locations`

Creates a new location of an opportunity.

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/locations/:id`

Returns a specific location with the following nested resources:

- [`phones`](locations/phones.md)
- [`schedule`](locations/schedule.md)

#### `PUT /v1/organizations/:organization_id/opportunities/:opportunity_id/locations/:id`

Updates a location of an opportunity.

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/locations/:id`

Deletes a location of an opportunity.

#### Permissions

* Only resource owners and admins can manage locations, schedules, and phone numbers.
