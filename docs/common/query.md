## Common Parameters

# Query Parameters

Certain resource collections allow for searching by various methods: `Organizations`, `Opportunities`, and `HousingProperties`.

### Endpoints

The resource collection endpoints are just the top-level endpoints and a `GET` method should be used:

- `GET /v1/organizations`
- `GET /v1/opportunities`
- `GET /v1/housing_properties`

### Parameters

The following groups of parameters can be used to query on any resource collection that supports them queries (for now just `Organizations` and `Opportunities`).

#### IDs Query

Parameter       | Type         | Description                                                   | Example
----------------|--------------|---------------------------------------------------------------|----------
`ids`           | `string`     | A comma-separated set of IDs, whose records will be returned. | `ids=3%2C49%2C2`

#### Attributes Query

Parameter     | Type                                | Description    | Example
--------------|-------------------------------------|-----------------------------------|----------
`attributes`  | Object of attribute key-value pairs | The attributes of the record type to filter the query by. The results are restricted to those records that match all provided attributes. | `attributes[name]=Delancey+Street+Foundation`

#### Related Records Query

Parameter   | Type       | Description                                       | Example
------------|------------|---------------------------------------------------|-----------
`related`   | `boolean`  | Flag to return related records. Should be `true`. | `related=1`
`id`        | `integer`  | The ID of the record to which related records should be found. | `id=3`


#### Search Query

A search query is contained within a top-level `query` parameter:

Parameter       | Type                         | Description | Example
----------------|------------------------------|---------------------------------------------------------------|----------
`query`         | Object containing search parameters  | This is the top-level parameter whose value is the set of search parameters (see below) | `query[text]=health+clinic&query[lat]=37.7823&query[long]=-122.46`

The `query` object is comprised of the following parameters:

Parameter     | Type            | Description                          | Example
--------------|-----------------|--------------------------------------|----------------------------
`text`        | `string`        | Keywords to use for full text searching . Surround the term in quotes (" ") for exact phrase matching. | `query[text]=health+clinic`
`attributes`  | Object          | Attributes matching, see _Attributes object_ below. | See below.
`lat`         | `decimal`       | The latitude around which to search.  | `query[lat]=37.7823`
`long`        | `decimal`       | The longitude around which to search. | `query[long]=122.46`
`distance`    | `decimal`       | The radius in kilometers around the coordinates specified in which to search. | `query[distance]=40.2336`
`order`       | `string`        | The ordering in which to return results. Options for `Opportunities` and `Organizations` are: `best`, `distance`, `popularity`, `newest`. For `HousingProperties`, options are: `best`, `earliest` (lowest wait list time), `rent` (lowest rent), and `newest` (most recently added). | `query[order]=best`.
`properties`  | Object of property key-value pairs | Specific properties can be specified to narrow search results by only records that match the given property key-value paris | `query[properties][lang-spanish]=true&query[properties][cost-free]=true`
`match`       | `string`        | Whether the results should match all attributes provided, or if the results should just be ordered by closeness to them. Possible values are `any`, which orders the results that match any given property, and `properties`, which ensures all results adhere to the properties given, and `by_type`, which will act to `OR` all properties within a property type family (e.g. `lang-`, `community-`, etc) and AND between property type families. One Degree's ([1deg.org](https://www.1deg.org)) basic search functionality uses `by_type` to filter. | `match=by_type`

Example:

    GET /v1/opportunities?api_key=API_KEY&query[text]=jobs&query[order]=relevance&query[distance]=40.2336&query[lat]=37.7822891&query[long]=-122.463708&query[properties][for-teens]=true&query[properties][lang-spanish]=true&page=1&per_page=10

##### Attributes object

To match to specific attributes on an object in a `query` search, use the `query[attributes]` parameter. This can then have an `and` object, an `or` object, or a directly nested field-operator-value object. Nested on `and` and `or` parameters are field-operator-value objects. Using `and` will return an resources that match *all* of the attributes specified. Using `or` matches resources that have *any* of the attributes specified.

Each field-operator-value object has the field name as the key, and then an object as the value, which contains an `operator` key-value pair, and a `value` key-value pair.

Operators can be any one of the follow: `equal_to`, `less_than`, `greater_than`, `less_than_or_equal_to`, `greater_than_or_equal_to`, `between`, `any_of`, `all_of`

For example, to retrieve all Housing Properties in Contra Costa or San Francisco, the parameters would be:

    { "query": {
        attributes": {
          "county": {
            "operator": "any_of",
            "value": ["San Francisco", "Contra Costa"]
          }
        }
    }

And the full request with query string, would look like:

    GET /v1/housing_properties?api_key=API_KEY&query[attributes][county][operator]=any_of&query[attributes][county][value][]=Contra+Costa&query[attributes][county][value][]=San+Francisco

For example, to retrieve all Housing Properties in Contra Costa or San Francisco, with maximum waitlist time of 12 months, the parameters would be:

    { "query": {
        attributes": {
          "and": {
            "county": {
              "operator": "any_of",
              "value": ["San Francisco", "Contra Costa"]
            },
            "waitlist_max": {
              "operator": "less_than_or_equal_to",
              "value": 12
            }
          }
        }
      }
    }

And the full request with query string, would look like:

    GET /v1/housing_properties?api_key=API_KEY&query[attributes][and][county][operator]=any_of&query[attributes][and][county][value][]=Contra+Costa&query[attributes][and][county][value][]=San+Francisco&query[attributes][and][waitlist_max][operator]=less_than_or_equal_to&query[attributes][and][waitlist_max][value]=12

See also [Pagination Parameters](/docs/common/pagination.md)
