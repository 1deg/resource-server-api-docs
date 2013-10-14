# Resources

## Opportunities on Service Providers

An opportunity represents an event, appointment, resource, or other offering that the organization makes available. Opportunities are specific, that is to say, they represent a discrete item that can be added to an end user's list of tasks.

An exmple might be a job training class, which meets at a specific time and place. An implementation of a task list might allow the user to add this training class to her schedule.

### Attributes

Field            | Type         | Note     | Description
-----------------|--------------|----------|--------------------------------
`id`             | `integer`    | auto     | Unique opportunity ID.
`title`          | `string`     | required | The name of the opportunity.
`is_appointment` | `boolean`    |          | Whether or not this is an appointment. Default is `false`.
`description`    | `text`       |          | The opportunity's description.
`requirements`   | `text`       |          | The opportunity's requirements.

### Endpoints

#### `GET /v1/organizations/:organization_id/opportunities`

Returns the list of opportunities on a organization with the following nested resources:

- [`properties`](/docs/organizations/opportunities/properties.md)
- [`tags`](/docs/organizations/opportunities/tags.md)
- [`locations`](/docs/organizations/opportunities/locations.md)

#### `POST /v1/organizations/:organization_id/opportunities`

Creates a new opportunity on a organization.

#### `PUT /v1/organizations/:organization_id/opportunities/:id`

Updates an opportunity.

#### `DELETE /v1/organizations/:organization_id/opportunities/:id`

Deletes an opportunity.
