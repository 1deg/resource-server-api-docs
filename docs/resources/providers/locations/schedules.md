# Resource

## Schedules on Locations

### Attributes

Field             | Type         | Optional | Description    
------------------|--------------|----------|---------------------------------
`start_on`        | `Datetime`   | yes      | A specific start date of the location's schedule.
`end_on`          | `Datetime`   | yes      | A specific start date of the location's schedule.
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
