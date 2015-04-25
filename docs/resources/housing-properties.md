## Resources

# Housing Properties

### Attributes

Field               | Type         | Note       | Description                                  
--------------------|--------------|------------|---------------------------------------
`id`                | `integer`    | read-only  | Unique housing property ID.
`slug`              | `string`     | read-only  | Unique housing property URL slug.
`name`              | `string`     | required   | The name of the housing property.
`website`           | `string`     |            | The URL of the housing property's website.
`description`       | `text`       |            | The description of the housing property.
`app_instructions`  | `text`       |            | Instructions on how to submit an application.
`address`           | `string`     |            | Street address of the housing property.
`city`              | `string`     |            |
`state`             | `string`     |            |
`zip_code`          | `string`     |            |
`county`            | `string`     |            |
`lat`               | `float`      |            |
`long`              | `float`      |            |
`waitlist_min`      | `integer`    |            | Minimum waitlist time, in months.
`waitlist_max`      | `integer`    |            | Maximum waitlist time, in months.
`waitlist_status`   | `string`     |            | Whether or not a waitlist is currently accepting new applications, or if it will happen between specific dates. Possible values are `open`, `closed`, `dates`.
`waitlist_note`     | `text`       |            |
`waitlist_open_date`  | `Date`     |            | When the waitlist will start to accept applications.
`waitlist_close_date` | `Date`     |            | When the waitlist will no longer accept applications.
`updated_at`        | `Datetime`   | read-only  | The timestamp of the last time the organization was updated.

Housing properties also have the following nested arrays and objects:

- `organization` (its parent resource)
- `units`
- `properties`
- `phones`
- `rental_office` (of the resource type `location`)
** `office_hours` (of the resource type `schedule`)
- `images`
- `attachments`

Units have the following attributes:

Field                   | Type         | Note       | Description                                  
------------------------|--------------|------------|---------------------------------------
`id`                    | `integer`    | read-only  | Unique unit ID.
`housing_property_id`   | `string`     | read-only  | Unique ID of the parent housing property resource.
`title`                 | `string`     |            | The name of the unit.
`bedrooms`              | `text`       |            | The number of bedrooms in the unit.
`income_min_by_period`  | `string`     |            | The time period type in which to calculate income minimum. Possible values are `monthly` and `annually`.
`income_max_by_period`  | `string`     |            | The time period type in which to calculate income maximum. Possible values are `monthly` and `annually`.
`income_min_by_rent`    | `float`      |            | A multiple of the rent, which is the minimum income required.
`income_note`           | `text`       |            | Text note about the income requirements.
`rent_monthly_min`      | `float`      |            | The minimum possible rent for this unit.
`rent_monthly_max`      | `float`      |            | The maximum possible rent for this unit.
`occupancy_min`         | `integer`    |            | The minimum number of occupants required.
`occupancy_max`         | `integer`    |            | The maximum number of occupants allowed.

### Endpoints

#### `GET /v1/housing_properties`

Returns a list of housing properties. [Pagination](/docs/common/pagination.md) and [query](/docs/common/query.md) parameters apply.

#### `GET /v1/housing_properties/:id`

Returns a specific housing property, along with the following nested objects:

- [`properties`](properties.md)
- [`tags`](tags.md)
- [`locations`](locations.md)
- [`phones`](phones.md)
- top 5 opportunity comments [`comments`](comments.md)

Example:

    {
      "id": 1,
      "name": "Say House",
      "description": "Sed posuere consectetur est at lobortis. Donec ullamcorper nulla non metus auctor fringilla. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.",
      "slug": "say-house-mercy-housing",
      "app_instructions": "Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor. Curabitur blandit tempus porttitor. Nullam id dolor id nibh ultricies vehicula ut id elit. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor. Maecenas sed diam eget risus varius blandit sit amet non magna.",
      "website": "",
      "address": "180 Townsend St",
      "city": "San Francisco",
      "state": "CA",
      "zip_code": "",
      "county": "San Francisco",
      "lat": 37.7793,
      "long": -122.393,
      "waitlist_min": 6,
      "waitlist_max": 12,
      "waitlist_status": "open",
      "waitlist_note": "",
      "phones": [
        {
          "id": 4536,
          "phoneable_id": 1,
          "phoneable_type": "HousingProperty",
          "digits": "555-1212",
          "phone_type": "",
          "is_primary": false,
          "created_at": "2015-04-22T14:43:20.000Z",
          "updated_at": "2015-04-22T14:43:20.000Z"
        }
      ],
      "rental_office": {
        "id": 2597,
        "name": "Rally Pad Rental Office",
        "address": "144 2nd St",
        "unit": "Lower Level",
        "city": "San Francisco",
        "state": "CA",
        "zip_code": "",
        "lat": 37.7873,
        "long": -122.399,
        "office_hours": {
          "id": 4864,
          "scheduleable_id": 2597,
          "scheduleable_type": "Location",
          "start_on": null,
          "end_on": null,
          "monday_start": "09:00",
          "monday_end": "17:00",
          "tuesday_start": "09:00",
          "tuesday_end": "17:00",
          "wednesday_start": "09:00",
          "wednesday_end": "17:00",
          "thursday_start": "09:00",
          "thursday_end": "17:00",
          "friday_start": "09:00",
          "friday_end": "17:00",
          "saturday_start": "",
          "saturday_end": "",
          "sunday_start": "",
          "sunday_end": "",
          "notes": "",
          "created_at": "2015-04-22T14:41:21.000Z",
          "updated_at": "2015-04-22T14:41:21.000Z"
        }
      },
      "images": [
        {
          "id": 10,
          "url": "http://localhost:3002/system/s3/image/HousingProperty_1_f4d96fa0cb2b0132340f2cf0ee0890e2_100x100.jpg",
          "dimensions": "100x100"
        }
      ],
      "attachments": [
        {
          "id": 6,
          "url": "/Users/eric/Dropbox/Projects/onedegree/resource-server/public/system/s3/attachment/OneDegree-for-Nonprofits-July-14-2014_1429713899.pdf",
          "display_name": "Application form",
          "file_type": "pdf"
        }
      ],
      "properties": {
        "lang-spanish": "true"
      },
      "units": [
        {
          "id": 6,
          "housing_property_id": 1,
          "title": "2 bedroom unit",
          "slug": "2-bedroom-unit-say-house",
          "bedrooms": 2,
          "income_min_by_period": "monthly",
          "income_max_by_period": "monthly",
          "income_min_by_rent": "2.0",
          "income_note": "",
          "rent_monthly_min": "990.0",
          "rent_monthly_max": "1100.0",
          "occupancy_min": 3,
          "occupancy_max": 4
        }
      ]
    }

#### `GET /v1/housing_properties/:id/get_slug`

Returns the URL "slug" or shortcut for the organization specified by its numeric ID.

    GET /v1/organizations/2/get_slug

    {
      "status": "OK",
      "slug": "say-house-mercy-housing"
    }
