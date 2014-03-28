## Resources

# Guides

### Attributes

Field             | Type              | Note        | Description                                  
------------------|-------------------|-------------|---------------------------------------
`id`              | `integer`         | read-only   | Unique resource ID.
`title`           | `string`          | required    | The name of the guide.
`description`     | `string`          |             | The description of what the guide is about.
`location`        | `text`            |             | The area for which the guide is applicable.
`parent_guide_id` | `integer`         | write-only  | The guide to which this guide should be assigned as a subguide.
`parent_guide`    | `Guide`           | read-only   | A Guide object that is the parent of this one.
`opportunity_ids` | `Array<integer>`  | read-only   | The opportunities that make up the contents of the guide.
`subguides`       | `Array<Guide>`    | read-only   | The guides that are more specific subcategories of the overall guide.

### Endpoints

#### `GET /v1/guides`

Returns the list of all top-level guides, meaning, they do not have parent guides. Standard pagination parameters apply.

#### `POST /v1/guides`

Creates a new guide.

#### `GET /v1/guides/:id`

Returns a specific guide.

#### `GET /v1/guides/:id/opportunities`

Returns the opportunity objects that are collected by this guide.
See [Opportunities](/opportunities.md) for
more information on opportunity objects.

#### `PUT /v1/guides/:id`

Updates a guide.

#### `DELETE /v1/guides/:id`

Deletes a guide.

### Permissions

* Anyone can create a guide.
* Only admins and the original creator can update a guide.
* Only admins can delete a guide.
