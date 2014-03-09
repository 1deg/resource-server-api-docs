# Resources

## Organizations

### Attributes

Field          | Type         | Note     | Description                                  
---------------|--------------|----------|---------------------------------------
`id`           | `integer`    | auto     | Unique organization ID.
`name`         | `string`     | required | The name of the organization.
`website`      | `string`     |          | The URL of the organization's website.
`description`  | `text`       |          | The description of the organization.
`updated_at`   | `string`     |          | The timestamp of the last time the organization was updated.

### Endpoints

#### `GET /v1/organizations`

Returns a list of organization. Standard pagination parameters apply.

#### `POST /v1/organizations`

Creates a new organization.

#### `GET /v1/organizations/:id`

Returns a specific organization, along with the following nested objects:

- [`properties`](/docs/resources/organizations/properties.md)
- [`tags`](/docs/resources/organizations/tags.md)
- [`locations`]()
- [`phones`]()
- top 5 opportunity [`comments`](/docs/resources/organizations/opportunities/comments.md)

Example:

    {
      "id": 3,
      "name": "ASIAN, Inc.",
      "slug": "asian-inc",
      "website": "http://asianinc.org/",
      "description": "ASIAN, Inc. empowers Asian Americans and other minorities by reducing dependencies that block their access to opportunities in business development, housing and financial education.",
      "updated_at": "2013-12-14T04:59:55.000Z",
      "opportunity_count": 4,
      "tags": [
          "housing",
          "home-buying",
          "affordable-housing"
      ],
      "properties": [
          {
              "name": "lang-mandarin",
              "value": "true"
          },
          {
              "name": "lang-cantonese",
              "value": "true"
          },
          {
              "name": "lang-english",
              "value": "true"
          }
      ],
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
      "opportunity_comments": [
          {
              "id": 6,
              "commentable_type": "Opportunity",
              "commentable_id": 9,
              "client_id": 4,
              "client_user_id": "311",
              "content": "Para mi esta aplcacion es de mucha ayuda gracias por ayudarme a aplicar veo q es de mucha ayuda",
              "created_at": "2014-02-25T05:37:14.000Z"
          }
      ]
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

### Permissions

* Anyone can add a new organization.
* Only admins and the original organization owner can update a organization.
* Only admins can delete a organization.
