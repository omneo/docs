# Rewards Definitions

This API allows you to create, read, update and delete reward definitions.

## Reward Definition Attributes

| Attribute       | Description                                                    |
|-----------------|----------------------------------------------------------------|
| id              | The ID of the reward definition                                |
| name            | The name of the reward definition                              |
| description     | The description of the reward definition                       |
| notes           | The notes of the reward definition                             |
| value           | The value of the rewards associate with this reward definition |
| period          | The number of days that its rewards can be redeemed            |
| is_extendable   | Whether its rewards can be extended                            |
| is_reassignable | Whether its rewards can be re-assigned to someone else         |
| max_redemptions | The maximum times its rewards can be redeemed                  |
| handle          | The handle of the reward definition                            |





## Create a reward definition

> JSON Response Example:
                
```json
{
    "data": {
        "id": 4,
        "name": "Birthday",
        "handle": "birthday",
        "period": 30,
        "description": "...",
        "notes": "xxx",
        "value": 20,
        "max_redemptions": 1,
        "is_extendable": false,
        "is_reassignable": null,
        "tags": [],
        "created_at": "2018-02-02 04:08:52",
        "updated_at": "2018-02-02 04:08:52"
    }
}
```

> JSON Request Example:

```json
{
  "name": "Birthday",
  "handle": "birthday",
  "period": 30,
  "description": "...",
  "notes": "xxx",
  "value": 20,
  "is_extendable": false,
  "max_redemptions": 1
}
```


This API allows you to create a reward definition.

### HTTP Request

`POST /api/v1/rewards/definitions`

### Request Attributes
| Attribute       | Type                             |
|-----------------|----------------------------------|
| name            | `required` `string`              |
| description     | `nullable` `string`              |
| notes           | `nullable` `string`              |
| value           | `required` `numeric`             |
| period          | `required` `integer`             |
| is_extendable   | `nullable` `boolean`             |
| max_redemptions | `nullable` `integer`             |
| handle          | `required` `alpha_dash` `unique` |
| tags            | `sometimes` `required` `array`   |
| tags.*.id       | `required` `exists`              |





## List all reward definitions

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "name": "maiores",
            "handle": "soluta-minus-ea-nostrum-sit-sit-mollitia",
            "period": 14,
            "description": "Sed eos eligendi perferendis sed temporibus deserunt. Ipsum maxime dolorem debitis laudantium. Quis vel ex fugit atque recusandae quidem. Est sit aut quia cumque corrupti voluptate culpa accusantium.",
            "notes": null,
            "value": 1985.07,
            "max_redemptions": 2955071,
            "is_extendable": true,
            "is_reassignable": false,
            "tags": [],
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-01-31 00:41:16"
        },
        {
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
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/rewards/definitions?page=1",
        "last": "http://omneo-api.dev/api/v1/rewards/definitions?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/rewards/definitions",
        "per_page": 15,
        "to": 3,
        "total": 3
    }
}
```

This API lets you list all reward definitions.

### HTTP Request

`GET /api/v1/rewards/definitions`



## Retrieve a reward definition

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "maiores",
        "handle": "soluta-minus-ea-nostrum-sit-sit-mollitia",
        "period": 14,
        "description": "Sed eos eligendi perferendis sed temporibus deserunt. Ipsum maxime dolorem debitis laudantium. Quis vel ex fugit atque recusandae quidem. Est sit aut quia cumque corrupti voluptate culpa accusantium.",
        "notes": null,
        "value": 1985.07,
        "max_redemptions": 2955071,
        "is_extendable": true,
        "is_reassignable": false,
        "tags": [],
        "created_at": "2018-01-31 00:41:16",
        "updated_at": "2018-01-31 00:41:16"
    }
}
```

This API lets you retrieve a single reward definition.

### HTTP Request

`GET /api/v1/rewards/definitions/{rewardDefinition}`



## Update a reward definition

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "Birthday Reward",
        "handle": "soluta-minus-ea-nostrum-sit-sit-mollitia",
        "period": 30,
        "description": "...",
        "notes": "xxx",
        "value": 20,
        "max_redemptions": 1,
        "is_extendable": false,
        "is_reassignable": false,
        "tags": [],
        "created_at": "2018-01-31 00:41:16",
        "updated_at": "2018-02-02 04:22:22"
    }
}
```

> JSON Request Example:
                
```json
{
  "name": "Birthday Reward",
  "period": 30,
  "description": "...",
  "notes": "xxx",
  "value": 20,
  "is_extendable": false,
  "max_redemptions": 1
}
```

This API lets you update a reward definition.

### HTTP Request

`PUT /api/v1/rewards/definitions/{rewardDefinition}`

### Request Attributes
| Attribute       | Type                             |
|-----------------|----------------------------------|
| name            | `sometimes` `required` `string`  |
| description     | `sometimes` `nullable` `string`  |
| notes           | `nullable` `string`              |
| value           | `sometimes` `required` `numeric` |
| period          | `sometimes` `required` `integer` |
| is_extendable   | `sometimes` `nullable` `boolean` |
| max_redemptions | `sometimes` `nullable` `integer` |
| tags            | `sometimes` `required` `array`   |
| tags.*.id       | `required` `exists`              |




## Delete a reward definition

This API lets you delete a reward definition.

### HTTP Request

`DELETE /api/v1/rewards/definitions/{rewardDefinition}`

