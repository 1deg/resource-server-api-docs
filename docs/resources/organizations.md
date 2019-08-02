## Resources

# Organizations

### Attributes

Field               | Type         | Note       | Description                                  
--------------------|--------------|------------|---------------------------------------
`id`                | `integer`    | read-only  | Unique organization ID.
`slug`              | `string`     | read-only  | Unique organization URL slug.
`name`              | `string`     | required   | The name of the organization.
`website`           | `string`     |            | The URL of the organization's website.
`description`       | `text`       |            | The description of the organization.
`region`            | `string`     |            | City and state (or any string Google Maps can geocode), representing the geographic area the organization is based.
`lat`               | `float`      | read-only  | Latitude of the region. Set automatically upon change in region.
`lng`               | `float`      | read-only  | Longitude of the region. Set automatically upon change in region.
`updated_at`        | `string`     | read-only  | The timestamp of the last time the organization was updated.
`opportunity_count` | `integer`    | read-only  | The number of opportunities the organization provides.
`rating`            | `decimal`    | read-only  | The average star rating given for this opportunity by users, aggregated across all API clients.

### Endpoints

#### `GET /v1/organizations`

Returns a list of organization. Standard [pagination](/docs/common/pagination.md) and [query](/docs/common/query.md) parameters apply.

#### `POST /v1/organizations`

Creates a new organization.

#### `GET /v1/organizations/:id`

Returns a specific organization, along with the following nested objects:

- [`properties`](properties.md)
- [`tags`](tags.md)
- [`locations`](locations.md)
- [`phones`](phones.md)
- `emails`
- top 5 opportunity comments [`comments`](comments.md)

`:id` can either be the numeric ID number or the `slug`, which is also unique across organizations.

Example:

    {
        "id": 802,
        "name": "Shepherd's Gate",
        "region": "Livermore, CA",
        "slug": "shepherd-s-gate",
        "website": "http://www.shepherdsgate.org",
        "description": "Shepard's Gate provides battered homeless women and children with shelter, medical care, counseling, educational courses, job training and more. ",
        "lat": 37.6819,
        "lng": -121.768,
        "updated_at": "2019-07-30T22:43:41.000Z",
        "resource_type": "Organization",
        "opportunity_count": 5,
        "tags": [],
        "properties": {
            "service-county-california-alameda": "true"
        },
        "locations": [
            {
                "id": 1420,
                "name": "New Life Thrift Store",
                "address": "4014 East Avenue",
                "city": "Livermore",
                "state": "CA",
                "zip_code": "94550",
                "lat": 37.681,
                "long": -121.748,
                "is_primary": false,
                "show_on_organization": true,
                "phones": [
                    {
                        "id": 19202,
                        "digits": "925-606-1924",
                        "phone_type": "Office",
                        "is_primary": false
                    }
                ],
                "schedule": {
                    "monday_start": "09:00",
                    "monday_end": "19:00",
                    "tuesday_start": "09:00",
                    "tuesday_end": "19:00",
                    "wednesday_start": "09:00",
                    "wednesday_end": "19:00",
                    "thursday_start": "09:00",
                    "thursday_end": "19:00",
                    "friday_start": "09:00",
                    "friday_end": "19:00",
                    "saturday_start": "09:00",
                    "saturday_end": "17:00"
                }
            },
            {
                "id": 3484,
                "name": "Livermore Campus",
                "address": "1660 Portola Ave",
                "city": "Livermore",
                "state": "CA",
                "zip_code": "94551",
                "lat": 37.6932,
                "long": -121.779,
                "is_primary": false,
                "show_on_organization": true,
                "phones": [
                    {
                        "id": 19203,
                        "digits": "888-216-4776",
                        "phone_type": "Office",
                        "is_primary": false
                    },
                    {
                        "id": 19204,
                        "digits": "925-449-3114",
                        "phone_type": "Fax",
                        "is_primary": false
                    }
                ],
                "schedule": {
                    "monday_start": "09:30",
                    "monday_end": "16:30",
                    "tuesday_start": "09:30",
                    "tuesday_end": "16:30",
                    "wednesday_start": "09:30",
                    "wednesday_end": "16:30",
                    "thursday_start": "09:30",
                    "thursday_end": "16:30"
                }
            },
            {
                "id": 3485,
                "name": "Brentwood Campus",
                "address": "605 Sycamore Ave",
                "city": "Brentwood",
                "state": "CA",
                "zip_code": "94513",
                "lat": 37.9403,
                "long": -121.685,
                "is_primary": false,
                "show_on_organization": true,
                "phones": [
                    {
                        "id": 19205,
                        "digits": "888-216-4776",
                        "phone_type": "Office",
                        "is_primary": false
                    }
                ],
                "schedule": {
                    "monday_start": "09:30",
                    "monday_end": "16:30",
                    "tuesday_start": "09:30",
                    "tuesday_end": "16:30",
                    "wednesday_start": "09:30",
                    "wednesday_end": "16:30",
                    "thursday_start": "09:30",
                    "thursday_end": "16:30"
                }
            }
        ],
        "phones": [
            {
                "id": 39178,
                "digits": "888-216-4776",
                "phone_type": "Phone",
                "is_primary": true
            },
            {
                "id": 39179,
                "digits": "925-449-3114",
                "phone_type": "Fax",
                "is_primary": false
            }
        ],
        "emails": [
            {
                "id": 1157,
                "email": "shepgate@shepherdsgate.org",
                "title": "",
                "first_name": "General information",
                "last_name": "",
                "is_primary": false,
                "show_on_organization": true
            }
        ],
        "rating": 0,
        "images": [],
        "opportunity_comments": [],
        "has_pending_submission": false,
        "last_verified_at": "2018-11-06T10:51:33.000Z"
    }

#### `GET /v1/organizations/:id/get_slug`

Returns the URL "slug" or shortcut for the organization specified by its numeric ID.

    GET /v1/organizations/2/get_slug

    {
      "status": "OK",
      "slug": "3rd-street-youth-center-and-clinic"
    }

#### `PUT /v1/organizations/:id`

Updates a organization.

#### `DELETE /v1/organizations/:id`

Deletes a organization.
