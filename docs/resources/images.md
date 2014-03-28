gi## Resources

# Images

### Attributes

Field        | Type      | Note       | Description                        
-------------|-----------|------------|------------------------------------
`id`         | `integer` | read-only  | The unique ID of the image.
`url`        | `string ` | read-only  | The public URL to the image. This is set automatically upon creation.
`dimensions` | `string`  | required   | The width and height properties of the image in `WxH` format
`file`       | `File`    | required   | The image file.
`filename`   | `string`  |            | The original file name of the file, e.g. `my_picture.jpg`.

### Endpoints on Organizations

#### `GET /v1/organizations/:organization_id/images`

Returns a list of the images on an organization.

#### `POST /v1/organizations/:organization_id/images`

Uploads an image for an organization. Only one image of the same dimensions can be uploaded for a given organization.

#### `DELETE /v1/organizations/:organization_id/images/:id`

Deletes an image from an organization.

### Endpoints on Opportunities

#### `GET /v1/organizations/:organization_id/opportunities/:opportunity_id/images`

Returns a list of the images on an opportunity.

#### `POST /v1/organizations/:organization_id/opportunities/:opportunity_id/images`

Uploads an image for an opportunity.

#### `DELETE /v1/organizations/:organization_id/opportunities/:opportunity_id/images/:id`

Deletes an image from an opportunity.


### Permissions

* Only the owner of the associated resource and admins can manage images.
