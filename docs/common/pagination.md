## Common Parameters

# Pagination Parameters

Most resource collections support pagination parameters to more finely control response volume.

### Parameters

The following groups of parameters can be used to query on any resource collection that supports it (`Organizations`, `Opportunities`, and `HousingProperties`).

 Parameter    | Type      | Description                                       | Example
--------------|-----------|---------------------------------------------------|--------------------
`page`        | `integer` | The page offset. The default is 1                 | `page=3`
`per_page`    | `integer` | The number of items to return. The default is 10. | `per_page=5`
`titles_only` | `boolean` | Whether or not to return full resource objects or just titles and basic info. | `titles_only=true`