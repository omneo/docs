# Rewards

This API allows you to read rewards.

## Reward Attributes

| Attribute            | Description                                       |
|----------------------|---------------------------------------------------|
| id                   | The ID of the reward                              |
| value_initial        | The initial value of the reward                   |
| value_remaining      | Current remaining value of the reward             |
| expires_at           | The expiry date of the reward                     |
| issue_at             | The date the reward was created                   |
| reward_definition_id | The reward definition associated with this reward |
| profile_id           | The profile associated with this reward           |



## List all Rewards

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 2,
            "value_initial": 2578.18,
            "value_remaining": 2578.18,
            "expires_at": "2004-01-22 09:11:49",
            "issued_at": "2004-01-09 09:11:49",
            "is_expired": true,
            "definition": {
                "id": 2,
                "name": "dolores",
                "handle": "exercitationem-et-explicabo-repudiandae-laboriosam-qui",
                "period": 13,
                "description": "Maxime quae voluptas placeat mollitia dolorem quis. Recusandae debitis non rerum. Sunt et nihil reiciendis sunt maiores adipisci ex excepturi.",
                "notes": null,
                "value": 2578.18,
                "max_redemptions": 221,
                "is_extendable": false,
                "is_reassignable": false,
                "tags": [],
                "created_at": "2018-01-31 00:41:16",
                "updated_at": "2018-01-31 00:41:16"
            },
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-01-31 00:41:16"
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/profiles/4/rewards?page=1",
        "last": "http://omneo-api.dev/api/v1/profiles/4/rewards?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/profiles/4/rewards",
        "per_page": 15,
        "to": 1,
        "total": 1
    }
}
```

This API lets you list all rewards associated with a certain profile.

### HTTP Request

`GET /api/v1/profiles/{profile}/rewards`



## Retrieve a reward

> JSON Response Example:
                
```json
{
    "data": {
        "id": 2,
        "value_initial": 2578.18,
        "value_remaining": 2578.18,
        "expires_at": "2004-01-22 09:11:49",
        "issued_at": "2004-01-09 09:11:49",
        "is_expired": true,
        "definition": {
            "id": 2,
            "name": "dolores",
            "handle": "exercitationem-et-explicabo-repudiandae-laboriosam-qui",
            "period": 13,
            "description": "Maxime quae voluptas placeat mollitia dolorem quis. Recusandae debitis non rerum. Sunt et nihil reiciendis sunt maiores adipisci ex excepturi.",
            "notes": null,
            "value": 2578.18,
            "max_redemptions": 221,
            "is_extendable": false,
            "is_reassignable": false,
            "tags": [],
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-01-31 00:41:16"
        },
        "created_at": "2018-01-31 00:41:16",
        "updated_at": "2018-01-31 00:41:16"
    }
}
```

This API lets you retrieve a single reward.

### HTTP Request

`GET /api/v1/profiles/{profile}/rewards/{reward}`
