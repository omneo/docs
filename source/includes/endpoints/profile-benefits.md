# Profile Benefits

This API allows you to read profile's benefits.

## Benefit Properties

| Property             | Description                                          |
|-----------------------|-----------------------------------------------------|
| id                    | The ID of the benefit                               |
| expires_at            | The expiry date of the benefit                      |
| issue_at              | The date the benefit was created                    |
| benefit_definition_id | The benefit definition associated with this benefit |
| profile_id            | The profile associated with this benefit            |
| is_redeemable         | Whether this benefit is still redeemable            |
| redemptions_remaining | Define how many times this benefit can be redeemed  |
| definition            | The benefit definition associated with this benefit |
| created_at            | The create datetime of this benefit                 |
| updated_at            | The last update datetime of this benefit            |



## List all Benefits

> JSON Response Example:
                
```json
{
    "data": 
    [
      {
          "id": 1,
          "expires_at": "1973-07-23 10:35:28",
          "issued_at": "1973-07-13 10:35:28",
          "is_expired": true,
          "is_redeemable": false,
          "redemptions_remaining": 7,
          "definition": {
              "id": 1,
              "name": "accusamus",
              "handle": "corporis-ex-officia-fugiat-laudantium",
              "period": 10,
              "description": "Est molestiae id placeat amet sed. Sint sequi eos nihil aut nostrum. Incidunt necessitatibus quas laborum rerum rerum aperiam deserunt. Voluptas saepe in dignissimos ratione quo explicabo.",
              "notes": "Saepe nostrum culpa labore. Id omnis enim perferendis fugit. Provident facilis ut officia ipsa. Et incidunt reiciendis delectus omnis eaque consequatur quia.",
              "max_redemptions": 7,
              "is_extendable": false,
              "is_reassignable": false,
              "tags": [],
              "created_at": "2018-02-12 05:51:22",
              "updated_at": "2018-02-12 05:51:22"
          },
          "created_at": "2018-02-12 05:51:22",
          "updated_at": "2018-02-12 05:51:22"
      }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/profiles/5/benefits?page=1",
        "last": "http://omneo-api.dev/api/v1/profiles/5/benefits?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/profiles/5/benefits",
        "per_page": 15,
        "to": 1,
        "total": 1
    }
}
```

This API lets you list all benefits associated with a certain profile.

### HTTP Request

`GET /api/v1/profiles/{profile}/benefits`



## Retrieve a benefit

> JSON Response Example:
                
```json
{
    "data":       
        {
              "id": 1,
              "expires_at": "1973-07-23 10:35:28",
              "issued_at": "1973-07-13 10:35:28",
              "is_expired": true,
              "is_redeemable": false,
              "redemptions_remaining": 7,
              "definition": {
                  "id": 1,
                  "name": "accusamus",
                  "handle": "corporis-ex-officia-fugiat-laudantium",
                  "period": 10,
                  "description": "Est molestiae id placeat amet sed. Sint sequi eos nihil aut nostrum. Incidunt necessitatibus quas laborum rerum rerum aperiam deserunt. Voluptas saepe in dignissimos ratione quo explicabo.",
                  "notes": "Saepe nostrum culpa labore. Id omnis enim perferendis fugit. Provident facilis ut officia ipsa. Et incidunt reiciendis delectus omnis eaque consequatur quia.",
                  "max_redemptions": 7,
                  "is_extendable": false,
                  "is_reassignable": false,
                  "tags": [],
                  "created_at": "2018-02-12 05:51:22",
                  "updated_at": "2018-02-12 05:51:22"
              },
              "created_at": "2018-02-12 05:51:22",
              "updated_at": "2018-02-12 05:51:22"
        }
}
```

This API lets you retrieve a single benefit.

### HTTP Request

`GET /api/v1/profiles/{profile}/benefits/{benefit}`
