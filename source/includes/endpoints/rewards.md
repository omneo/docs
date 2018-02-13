## Rewards

This API allows you to read all rewards or retrieve a single rewards.

### Reward Attributes

| Attribute            | Description                                       |
|----------------------|---------------------------------------------------|
| id                   | The ID of the reward                              |
| value_initial        | The initial value of the reward                   |
| value_remaining      | Current remaining value of the reward             |
| expires_at           | The expiry date of the reward                     |
| issue_at             | The date the reward was created                   |
| is_expired           | Whether the reward is expired or not              |
| definition           | The reward definition associated with this reward |
| created_at           | The create date of this reward                    |
| updated_at           | The last update date of this reward               |




### List all Rewards

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "value_initial": 2120.39,
            "value_remaining": 2120.39,
            "expires_at": "1982-09-30 03:02:06",
            "issued_at": "1982-09-18 03:02:06",
            "is_expired": true,
            "definition": {
                "id": 1,
                "name": "laborum",
                "handle": "cumque-asperiores-sequi-esse",
                "period": 12,
                "description": "Fugit dolores quae eius quam eum et. Sit modi quis cumque aut. Consectetur id in dolorem quod quod omnis.",
                "notes": null,
                "value": 2120.39,
                "max_redemptions": 3,
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
        "first": "http://omneo-api.dev/api/v1/profiles/9/rewards?page=1",
        "last": "http://omneo-api.dev/api/v1/profiles/9/rewards?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/profiles/9/rewards",
        "per_page": 15,
        "to": 1,
        "total": 1
    }
}
```

This API lets you list all rewards in the system with pagination.

#### HTTP Request

`GET /api/v1/rewards`

### Retrieve a rewards
>>>>>>> Stashed changes

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "value_initial": 2120.39,
        "value_remaining": 2120.39,
        "expires_at": "1982-09-30 03:02:06",
        "issued_at": "1982-09-18 03:02:06",
        "is_expired": true,
        "definition": {
            "id": 1,
            "name": "laborum",
            "handle": "cumque-asperiores-sequi-esse",
            "period": 12,
            "description": "Fugit dolores quae eius quam eum et. Sit modi quis cumque aut. Consectetur id in dolorem quod quod omnis.",
            "notes": null,
            "value": 2120.39,
            "max_redemptions": 3,
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

This API lets you retrieve a single reward.

#### HTTP Request

`GET /api/v1/rewards/{reward}`
