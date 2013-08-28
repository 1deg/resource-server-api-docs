# Resources

## Opportunities on Service Providers

An opportunity represents an event, appointment, resource, or other offering that the provider makes available. Opportunities are specific, that is to say, they represent a discrete item that can be added to an end user's list of tasks.

An exmple might be a job training class, which meets at a specific time and place. An implementation of a task list might allow the user to add this training class to her schedule.

### Attributes

Field            | Type         | Optional | Description
-----------------|--------------|-----------|--------------------------------
`id`             | `integer`    |           | Unique opportunity ID.
`title`          | `string`     |           | The name of the opportunity.
`is_appointment` | `boolean`    |           | Whether or not this is an appointment.
`description`    | `text`       | yes       | The opportunity's description.
`requirements`   | `text`       | yes       | The opportunity's requirements.

### Endpoints

#### `GET resources/:resource_id/opportunities`

Returns the list of opportunities on a provider with the following nested resources:

- [`properties`](/docs/providers/opportunities/properties.md)
- [`tags`](/docs/providers/opportunities/tags.md)
- [`locations`](/docs/providers/opportunities/locations.md)

#### `POST resources/:resource_id/opportunities`

Creates a new opportunity on a provider.

#### `PUT resources/:resource_id/opportunities/:id`

Updates an opportunity.

#### `DELETE resources/:resource_id/opportunities/:id`

Deletes an opportunity.
