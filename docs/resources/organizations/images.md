# Resources

## Images on Resource Providers

### Attributes

Field        | Type      | Note     | Description                        
-------------|-----------|----------|------------------------------------
`id`         | `integer` | auto     | The unique ID of the image.
`url`        | `string ` | auto     | The public URL to the image. This is set automatically upon creation.
`dimensions` | `string`  | required | The width and height properties of the image in `WxH` format
`file`       | `File`    | required | The image file.
`filename`   | `string`  |          | The original file name of the file, e.g. `my_picture.jpg`.

### Endpoints

#### `GET /v1/organizations/:organization_id/images`

Returns a list of the images on a organization.

#### `POST /v1/organizations/:organization_id/images`

Uploads an image to a organization. Only one image of the same dimensions can be uploaded for a given resource.

#### `DELETE /v1/organizations/:organization_id/images/:id`

Deletes an image from a organization.

### Permissions

* Only the owner of the associated organization and admins can manage images.
