## Resources

# Submissions

### Attributes

Field                   | Type              | Note        | Description                                  
------------------------|-------------------|-------------|---------------------------------------
`id`                    | `integer`         | read-only   | Unique resource ID.
`client_id`             | `integer`         | read-only   | The ID of the API client that created the submission (e.g. My Website's API key)
`client_user_id`        | `integer`         | required    | The unique identifier of the user that created the submission. Arbitrarily decided by API client.
`parent_resource_id`    | `integer`         |             | The parent of the resource for which this submission is being created (e.g. a submission to update an opportunity, whose parent organization has this ID).
`parent_resource_type`  | `string`          |             | The parent of the resource for which this submission is being created (e.g. a submission to update an opportunity, whose parent organization has "Organization" as the resource type).
`resource_id`           | `integer`         |             | The ID of the existing resource being updated by this submission. If this is a new resource, this will be blank.
`resource_type`         | `string`          |             | The type of the resource for which this submission is being created (e.g. "Opportunity" or "Organization").
`status`                | `integer`         | read-only   | Whether or not this submission has been approved. Options are `0` = pending, `1` = approved, `2` = rejected. Defaults to pending (0).
`message`               | `string`          | read-only   | Any message that should be sent to the submitter after either approval or rejection.
`content`               | `string`          |             | JSON representation of the resource with any proposed changes. JSON should follow same schema as resources sent back from the server.
`final_content`         | `string`          | read-only   | The JSON that was finally published, which may include changes added by the reviewer of the submission.
`original_content`      | `string`          | read-only   | The JSON that was originally submitted by the user with proposed changes, prior to any changes from the reviewer.
`reviewer_client_id`    | `integer`         |             | The ID of the API client on which the submission was reviewed and approved or rejected (e.g. One Degree's submission review admin panel).
`reviewer_client_reviewer_id` | `integer`   |             | The unique identifier of the user that reviewed the submission before being published. Arbitrarily decided by API client.
`new_resource_id`       | `integer`         | read-only   | If the submission created a new resource, this is set to that new resource's ID.
`submitter_type`        | `string`          |             | Arbitrary value that denotes what type of user made the submission. Helpful for logging and resource verification by the One Degree team.
`pending_update`        | `boolean`         | read-only   | Temporarily set upon a submission being queued for approval. Approval (publishing) of submissions happens in a background job because it can be a long-running task. Submissions where `pending_update` is `true` should not be modified.
`created_at`            | `datetime`        | read-only   |
`updated_at`            | `datetime`        | read-only   |

### Endpoints

#### `GET /v1/submissions`

Returns list of submissions. Standard pagination parameters apply.

#### `POST /v1/submissions`

Creates a new submission.

##### Request

    {
      "submission": {
        "resource_type": "Opportunity"
        "parent_resource_id": 3292
        "parent_resource_type": "Organization"
        "client_user_id": 131399
        "content": [Opportunity JSON with proposed changes]
        "submitter_type": "AffiliatedAdmin"  // Arbitrary
      }
    }
