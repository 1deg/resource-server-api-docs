## Resources

# Opportunities

An opportunity represents an event, appointment, resource, or other offering that the organization makes available. Opportunities are specific, that is to say, they represent a discrete item that can be added to an end user's list of tasks.

An example might be a job training class, which meets at a specific time and place. An implementation of a task list might allow the user to add this training class to her schedule.

### Attributes

Field            | Type         | Note      | Description
-----------------|--------------|-----------|--------------------------------
`id`             | `integer`    | read-only | Unique opportunity ID.
`slug`           | `string`     | read-only | Unique opportunity URL slug.
`title`          | `string`     | required  | The action-oriented sentence written in the second-person (e.g. "Take a computer class")
`is_appointment` | `boolean`    |           | Whether or not this is an appointment. Default is `false`.
`description`    | `text`       |           | The details of the opportunity.
`requirements`   | `text`       |           | The answer to the question, "what to do next?"
`rating`         | `decimal`    | read-only | The average star rating given for this opportunity by users, aggregated across all API clients.

### Endpoints

#### `GET /v1/opportunities`

Because they are the focal point of service provider information, Opportunities can be queried directly on the top-level endpoint without specifying an organization. Standard [pagination](/docs/common/pagination.md) and [query](/docs/common/query.md) parameters apply.

#### `GET /v1/organizations/:organization_id/opportunities`

Returns the list of opportunities on a organization with the following nested resources:

- [`properties`](properties.md)
- [`tags`](tags.md)
- [`locations`](locations.md)
- [`schedule`](schedule.md)
- [`phones`](phones.md)
- [`schedule`](phones.md)
- [`organization`](organizations.md) (some top-level information)

An example request:

      {
        "id": 3,
        "title": "Attend a workshop to learn more about the home purchase process",
        "description": "This workshop teaches the basics of the home purchase process and helps attendees make informed decisions.  Workshops are offered in Cantonese and Mandarin.",
        "requirements": "Show up for the monthly workshop",
        "slug": "attend-a-workshop-to-learn-more-about-the-home-purchase-process",
        "is_appointment": true,
        "tags": [
            "affordable-housing",
            "home-buying",
            "housing"
        ],
        "schedule": {
            "monday_start": "",
            "monday_end": "",
            "tuesday_start": "",
            "tuesday_end": "",
            "wednesday_start": "",
            "wednesday_end": "",
            "thursday_start": "",
            "thursday_end": "",
            "friday_start": "",
            "friday_end": "",
            "saturday_start": "",
            "saturday_end": "",
            "sunday_start": "",
            "sunday_end": "",
            "notes": ""
        },
        "properties": {
            "lang-mandarin": "true",
            "lang-cantonese": "true",
            "lang-english": "true"
        },
        "locations": [
            {
                "id": 3,
                "name": "Primary Location",
                "address": "1167 Mission Street",
                "unit": "4th Floor",
                "city": "San Francisco",
                "state": "CA",
                "zip_code": "94103",
                "lat": 37.7778,
                "long": -122.412,
                "is_primary": true,
                "phones": [
                    {
                        "id": 3,
                        "digits": "4159285910",
                        "phone_type": "Office",
                        "is_primary": true
                    }
                ],
                "schedule": {
                    "monday_start": "",
                    "monday_end": "",
                    "tuesday_start": "",
                    "tuesday_end": "",
                    "wednesday_start": "",
                    "wednesday_end": "",
                    "thursday_start": "",
                    "thursday_end": "",
                    "friday_start": "",
                    "friday_end": "",
                    "saturday_start": "",
                    "saturday_end": "",
                    "sunday_start": "",
                    "sunday_end": "",
                    "notes": ""
                }
            }
        ],
        "phones": [
            {
                "id": 4,
                "digits": "415-928-5910",
                "phone_type": "Office",
                "is_primary": true
            }
        ],
        "rating": 0,
        "organization": {
            "id": 3,
            "name": "ASIAN, Inc.",
            "slug": "asian-inc",
            "opportunity_count": 4
        }
      }

    
#### `POST /v1/organizations/:organization_id/opportunities`

Creates a new opportunity on an organization.

#### `PUT /v1/organizations/:organization_id/opportunities/:id`

Updates an opportunity.

#### `DELETE /v1/organizations/:organization_id/opportunities/:id`

Deletes an opportunity.
