## Resources

# Access Instructions on Opportunities

### Attributes

Field           | Type         | Note       | Description                           
----------------|--------------|------------|------------------------------------
`access_type`   | `string`     |            | The type of access this is. Options are `link`, `location`, `phone`, `other`, `email`, `file`
`instructions`        | `string` |          | The instructions for what to do to access this opportunity.
`access_value`    | `boolean`    |          | The contact information (phone, URL, etc.) to use for this instruction. Emails and locations are added as child objects (see `locations` and `emails`).
`meta_data`     | `string`     |            | String in JSON format that may contain additional data about this access instruction.
`enable_direct_access` | `boolean` | Defaults to `false` | Denotes if this organization accepts the sending of prospective client information directly to them via the contact information in this access instruction.
`locations`     | Array       | Of `location` objects | The email addresses that can be contacted for this access instruction.
`emails`        | Array       | Of `email` objects | The email addresses that can be contacted for this access instruction.

### Endpoints on Opportunities

#### `GET /v1/organizations/:organization_id/opportunities/:id/access_instructions`

Returns all access instructions on an opportunity.
