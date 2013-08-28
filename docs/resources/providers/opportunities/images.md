# Resources

## Images on Opportunities

### Attributes

Field        | Type      | Optional | Description                        
-------------|-----------|----------|------------------------------------
`id`         | `integer` |          | The unique ID of the image.
`url`        | `string ` | auto     | The public URL to the image. This is set automatically upon creation.
`dimensions` | `string`  |          | The width and height properties of the image in `WxH` format
`file`       | `File`    |          | The image file.
`filename`   | `string`  | yes      | The original file name of the file, e.g. `my_picture.jpg`.

### Endpoints

#### `GET resources/:resource_id/opportunities/:opportunity_id/images`

Returns a list of the images on a provider.

#### `POST resources/:resource_id/opportunities/:opportunity_id/images`

Uploads an image to a resource provider. Only one image of the same dimensions can be uploaded for a given resource.

#### `DELETE resources/:resource_id/opportunities/:opportunity_id/images/:id`

Deletes an image from a provider.

### Permissions

* Only the owner of the associated resource provider and admins can manage images.
