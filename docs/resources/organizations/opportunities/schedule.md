# Resource

## Schedule on Opportunities

Only one schedule can exist on an opportunity.

### Attributes

[See Schedule attributes here.](/docs/resources/organizations/schedules.md)

### Endpoints

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/locations/:id/schedule`

Creates a schedule on a location. Only one schedule can exist for a location.

#### `PUT /v1/organizations/:organization_id/opportunities/:opportunity_id/locations/:id/schedule`

Updates a location's schedule.

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/locations/:id/schedule`

Deletes the location's schedule.
