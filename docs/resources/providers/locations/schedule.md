# Resource

## Schedule on Locations

Only one schedule can exist on a location.

### Attributes

Field             | Type         | Note     | Description    
------------------|--------------|----------|---------------------------------
`start_on`        | `Datetime`   |          | A specific start date of the location's schedule.
`end_on`          | `Datetime`   |          | A specific start date of the location's schedule.
`monday_start`    | `string`     |          | The Monday opening hour of the location.
`monday_end`      | `string`     |          | The Monday closing hour of the location.
`tuesday_start`   | `string`     |          | The Tuesday opening hour of the location.
`tuesday_end`     | `string`     |          | The Tuesday closing hour of the location.
`wednesday_start` | `string`     |          | The Wednesday opening hour of the location.
`wednesday_end`   | `string`     |          | The Wednesday closing hour of the location.
`thursday_start`  | `string`     |          | The Thursday opening hour of the location.
`thursday_end`    | `string`     |          | The Thursday closing hour of the location.
`friday_start`    | `string`     |          | The Friday opening hour of the location.
`friday_end`      | `string`     |          | The Friday closing hour of the location.
`saturday_start`  | `string`     |          | The Saturday opening hour of the location.
`saturday_end`    | `string`     |          | The Saturday closing hour of the location.
`sunday_start`    | `string`     |          | The Sunday opening hour of the location.
`sunday_end`      | `string`     |          | The Sunday closing hour of the location.
`notes`           | `text`       |          | Any additional notes about the schedule. For example: holiday hours or early closures.

All hours `string` fields are of the format:

    HH:mm

### Endpoints

#### `POST resources/:resource_id/locations/:id/schedule`

Creates a schedule on a location. Only one schedule can exist for a location.

#### `PUT resources/:resource_id/locations/:id/schedule`

Updates a location's schedule.

#### `DELETE resources/:resource_id/locations/:id/schedule`

Deletes the location's schedule.
