## Common Parameters

# Query Parameters

Certain resource collections allow for searching by various methods. Currently, only the `Organizations` and `Opportunities` collections support these query parameters.

### Endpoints

The resource collection endpoints are just the top-level endpoints and a `GET` method should be used:

- `GET /v1/organizations`
- `GET /v1/opportunities`

### Parameters

The following groups of parameters can be used to query on any resource collection that supports them queries (for now just `Organizations` and `Opportunities`).

#### IDs Query

Parameter       | Type         | Description                                                   | Example
----------------|--------------|---------------------------------------------------------------|----------
`ids`           | `string`     | A comma-separated set of IDs, whose records will be returned. | `ids=3%2C49%2C2`

#### Attributes Query

Parameter     | Type                                | Description    | Example
--------------|-------------------------------------|-----------------------------------|----------
`attributes`  | Object of attribute key-value pairs | The attributes of the record type to filter the query by. | `attributes[name]=Delancey+Street+Foundation`

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

Parameter      | Type            | Description                          | Example
--------------|-----------------|---------------------------------------|----------------------------
`text`        | `string`        | The search keywords. Surround the term in quotes (" ") for exact phrase matching. | `query[text]=health+clinic`
`lat`         | `decimal`       | The latitude around which to search.  | `query[lat]=37.7823`
`long`        | `decimal`       | The longitude around which to search. | `query[long]=122.46`
`distance`    | `decimal`       | The radius in kilometers around the coordinates specified in which to search. | `query[distance]=40.2336`
`order`       | `string`        | The ordering in which to return results. Options are: `best`, `distance`, `popularity`, `newest`. | `query[order]=best`
`properties`  | Object of property key-value pairs | Specific properties can be specified to narrow search results by only records that match the given property key-value paris | `query[properties][lang-spanish]=true&query[properties][cost-free]=true`

Example:

    GET /v1/opportunities?api_key=API_KEY&query[text]=jobs&query[order]=relevance&query[distance]=40.2336&query[lat]=37.7822891&query[long]=-122.463708&query[properties][for-teens]=true&query[properties][lang-spanish]=true&page=1&per_page=10


    {
      "paging": {
          "total_count": 3,
          "per_page": 10,
          "current_page": 1,
          "total_pages": 1,
          "previous_page": null,
          "next_page": null,
          "first_page": "http://localhost:3002/v1/opportunities?api_key=f31419b01a7b0131a22a10ddb1da427e&order=id_asc&page=1&per_page=10",
          "last_page": "http://localhost:3002/v1/opportunities?api_key=f31419b01a7b0131a22a10ddb1da427e&order=id_asc&page=1&per_page=10"
      },
      "opportunities": [
          {
              "id": 61,
              "title": "Get two years or more of live-in education and job training",
              "description": "If you've hit bottom (drug- or alcohol use, violence, or homelessness) Delancey Street will help you turn your life around by training you for future employment. Residents get useful job skills that can be applied to future employment. There is a minimum stay of two years.",
              "requirements": "At any time, 24 hours a day, 7 days a week, you visit Delancey Street and get interviewed for admission during your visit. You must be willing to commit to remaining with Delancey for two years. Read more information here: http://www.delanceystreetfoundation.org/admission.php",
              "slug": "get-two-years-or-more-of-live-in-education-and-job-training",
              "is_appointment": false,
              "tags": [
                  "alcohol",
                  "drugs",
                  "health",
                  "shelter",
                  "housing",
                  "skills-training",
                  "learning",
                  "career-counseling",
                  "money"
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
                  "lang-english": "true",
                  "lang-spanish": "true",
                  "for-adults": "true",
                  "for-young-adults": "true",
                  "for-teens": "true",
                  "geo-neighborhood": "SoMa, South Beach",
                  "cost-fees": "Free",
                  "elig-description": "No hard and fast criteria exist other than a strong motivation to change one’s lifestyle, an ability to interact in an active fast paced environment, and reasonably good health."
              },
              "locations": [
                  {
                      "id": 34,
                      "name": "Delancey Street San Francisco",
                      "address": "600 Embarcadero ",
                      "unit": "",
                      "city": "San Francisco",
                      "state": "CA",
                      "zip_code": "94107",
                      "lat": 37.7844,
                      "long": -122.388,
                      "is_primary": true,
                      "phones": [
                          {
                              "id": 72,
                              "digits": "415-512-5104",
                              "phone_type": "",
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
                          "notes": "Open 24 hours per day/7 days per week."
                      }
                  }
              ],
              "phones": [
                  {
                      "id": 73,
                      "digits": "415-512-5104",
                      "phone_type": "",
                      "is_primary": true
                  }
              ],
              "rating": 0,
              "organization": {
                  "id": 25,
                  "name": "Delancey Street Foundation",
                  "slug": "delancey-street-foundation",
                  "opportunity_count": 1
              }
          },
          {
              "id": 162,
              "title": "Apply for a program to help high school students get into and graduate from college",
              "description": "Juma students get support through the college selection and application process, while also receiving a part-time job in one of Juma's concession business. Jobs start with a skills-training program, and the program provides personal coaching from Juma staff, and perks like college tours, financial guidance, tutoring and SAT prep.",
              "requirements": "Apply by downloading the application here: http://www.jumaventures.org/students/apply-now. Juma recruits students in February through March of each year.",
              "slug": "apply-for-a-program-to-help-high-school-students-get-into-and-graduate-from-college",
              "is_appointment": false,
              "tags": [
                  "money",
                  "learning",
                  "college",
                  "skills-training"
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
                  "lang-spanish": "true",
                  "for-teens": "true",
                  "for-young-adults": "true",
                  "elig-age-or-over": "13",
                  "action-signup-url": "http://www.jumaventures.org/students/apply-now",
                  "action-signup-website-description": "Download application on their website"
              },
              "locations": [
                  {
                      "id": 85,
                      "name": "Main Office",
                      "address": "131 Steuart Street",
                      "unit": "Suite 201",
                      "city": "San Francisco",
                      "state": "CA",
                      "zip_code": "94105",
                      "lat": 37.7929,
                      "long": -122.393,
                      "is_primary": true,
                      "phones": [
                          {
                              "id": 182,
                              "digits": "415.371.0727",
                              "phone_type": "Main Office",
                              "is_primary": true
                          },
                          {
                              "id": 183,
                              "digits": "415.371.1634",
                              "phone_type": "Fax",
                              "is_primary": false
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
              "phones": [],
              "rating": 0,
              "organization": {
                  "id": 52,
                  "name": "Juma Ventures",
                  "slug": "juma-ventures",
                  "opportunity_count": 1
              }
          },
          [...etc...]
      ]
    }
See also [Pagination Parameters](/docs/common/pagination.md)