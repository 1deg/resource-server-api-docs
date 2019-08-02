## Resources

# Emails

### Attributes

Field           | Type         | Note       | Description                           
----------------|--------------|------------|------------------------------------
`id`            | `integer`    | read-only  | The unique ID of the phone number.
`email`         | `string`     | required   | The email address.
`first_name`    | `string`     |            | The first name whose email this is.
`last_name`     | `string`     |            | The last name whose email this is.
`title`         | `string`     |             | The job title of the person whose email this is.
`is_primary`    | `boolean`    |            | Whether or not this is the opportunity's primary email. Defaults to `false`, unless this is the only email address.
`show_on_organization` | `boolean` | Defaults to `false` | Whether or not this email can also be given for the opportunity's parent organization (or is it specific to the opportunity).

### Endpoints on Opportunities

#### `GET /v1/organizations/:organization_id/opportunities/:id/emails`

Returns all email addresses for an opportunity.
