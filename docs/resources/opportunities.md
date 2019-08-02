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
`description`    | `text`       |           | The details of the opportunity.
`rating`         | `decimal`    | read-only | The average star rating given for this opportunity by users, aggregated across all API clients.

### Endpoints

#### `GET /v1/opportunities`

Because they are the focal point of service provider information, Opportunities can be queried directly on the top-level endpoint without specifying an organization. Standard [pagination](/docs/common/pagination.md) and [query](/docs/common/query.md) parameters apply.

#### `GET /v1/opportunities/:id`

Returns the opportunity with ID `:id`. `:id` can either be the numeric ID number or the `slug`, which is also unique across opportunities.

#### `GET /v1/organizations/:organization_id/opportunities`

Returns the list of opportunities on a organization with the following nested resources:

- [`properties`](properties.md)
- [`tags`](tags.md)
- [`locations`](locations.md)
- [`schedule`](schedule.md)
- [`phones`](phones.md)
- [`emails`](emails.md)
- [`schedule`](phones.md)
- [`access_instructions`](access_instructions.md)
- [`organization`](organizations.md) (some top-level information)

An example request:

      {
        "id": 5460,
        "title": "Get long-term shelter for women and children",
        "description": "The Shepherd's Gate 12-18 month long program provides women with or without children with long-term housing. Participants receive case management, recovery, counseling, job skills training, and childcare. ",
        "slug": "get-long-term-shelter-for-women-and-children",
        "is_appointment": true,
        "available_on": null,
        "expires_on": null,
        "region": null,
        "organization": {
            "id": 802,
            "name": "Shepherd's Gate",
            "slug": "shepherd-s-gate",
            "opportunity_count": 5,
            "resource_type": "Organization"
        },
        "resource_type": "Opportunity",
        "tags": [
            "Transitional housing",
            "Case management",
            "Housing"
        ],
            "categories": [
            "Temporary housing",
            "Family support services"
        ],
        "areas": [
            "Housing",
            "Family & Household"
        ],
        "schedule": {},
        "properties": {
            "community-children": "true",
            "elig-gender": "Female",
            "action-signup-url": "https://www.shepherdsgate.org/Program-Intake",
            "community-mothers": "true",
            "elig-homeless": "true",
            "cost-free": "true",
            "service-county-california-alameda": "true",
            "service-county-california-contra-costa": "true",
            "community-pregnant": "true",
            "community-domestic-violence-victim-survivor": "true",
            "community-post-incarceration": "true",
            "community-immigrant": "true"
        },
        "locations": [
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
                "id": 6692,
                "digits": "925-487-4147",
                "phone_type": "Livermore Campus Intake",
                "is_primary": false
            },
            {
                "id": 6693,
                "digits": "925-308-7507 x 307",
                "phone_type": "Brentwood Campus Intake",
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
        "attachments": [],
        "images": [],
        "access_instructions": [
            {
                "id": 3901,
                "access_value": "https://www.shepherdsgate.org/Program-Intake",
                "access_type": "link",
                "instructions": "Visit the link and select the preferred location to complete the intake form.",
                "enable_direct_access": false,
                "locations": [],
                "emails": []
            },
            {
                "id": 3902,
                "access_value": "Call the preferred location to begin the intake process.",
                "access_type": "other",
                "instructions": "",
                "enable_direct_access": false,
                "locations": [],
                "emails": []
            }
        ],
        "rating": 0,
        "has_pending_submission": false,
        "last_verified_at": "2019-07-30T22:58:52.000Z",
        "updated_at": "2019-07-30T22:58:52.000Z"
    }

    
#### `POST /v1/organizations/:organization_id/opportunities`

Creates a new opportunity on an organization.

#### `PUT /v1/organizations/:organization_id/opportunities/:id`

Updates an opportunity.

#### `DELETE /v1/organizations/:organization_id/opportunities/:id`

Deletes an opportunity.
