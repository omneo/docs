# Benefits Definitions

This API allows you to create, read, update and delete benefit definitions.

## Benefit Definition Attributes

| Attribute       | Description                                                     |
|-----------------|-----------------------------------------------------------------|
| id              | The ID of the benefit definition                                |
| name            | The name of the benefit definition                              |
| description     | The description of the benefit definition                       |
| notes           | The notes of the benefit definition                             |
| period          | The number of days that its benefits can be redeemed            |
| is_extendable   | Whether its benefits can be extended                            |
| is_reassignable | Whether its benefits can be re-assigned to someone else         |
| max_redemptions | The maximum times its benefits can be redeemed                  |
| handle          | The handle of the benefit definition                            |





## Create a benefit definition

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
        "max_redemptions": 1,
        "is_extendable": false,
        "is_reassignable": null,
        "tags": [],
        "created_at": "2018-02-02 04:42:33",
        "updated_at": "2018-02-02 04:42:33"
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
  "is_extendable": false,
  "max_redemptions": 1
}
```


This API allows you to create a benefit definition.

### HTTP Request

`POST /api/v1/benefits/definitions`

### Request Attributes
| Attribute       | Type                             |
|-----------------|----------------------------------|
| name            | `required` `string`              |
| description     | `nullable` `string`              |
| notes           | `nullable` `string`              |
| period          | `required` `integer`             |
| is_extendable   | `nullable` `boolean`             |
| max_redemptions | `nullable` `integer`             |
| handle          | `required` `alpha_dash` `unique` |
| tags            | `sometimes` `required` `array`   |
| tags.*.id       | `required` `exists`              |





## List all benefit definitions

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "name": "minima",
            "handle": "dolorem-veritatis-quo-exercitationem",
            "period": 13,
            "description": "Quos aliquam sunt deserunt nobis blanditiis culpa temporibus. Et quidem non quis voluptatum blanditiis sunt eum laudantium. Maxime alias officiis nihil culpa.",
            "notes": "Perspiciatis laborum sed quis aut iure. Ratione libero omnis inventore libero. Quisquam exercitationem exercitationem debitis autem aut.",
            "max_redemptions": 667401,
            "is_extendable": false,
            "is_reassignable": false,
            "tags": [],
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-01-31 00:41:16"
        },
        {
            "id": 2,
            "name": "architecto",
            "handle": "earum-sed-doloremque-maxime-minima",
            "period": 13,
            "description": "Ab est beatae cumque et soluta harum. Repellat impedit ab ea est in molestias. Rem et corporis quaerat accusamus. Laudantium eligendi saepe sit autem recusandae. Itaque qui est sunt atque reiciendis.",
            "notes": "Consequatur qui temporibus cupiditate est quis. Quidem voluptatum soluta autem et enim quibusdam. Pariatur dicta sed occaecati. Est ea non autem maiores ducimus.",
            "max_redemptions": 7,
            "is_extendable": true,
            "is_reassignable": true,
            "tags": [],
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-01-31 00:41:16"
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/benefits/definitions?page=1",
        "last": "http://omneo-api.dev/api/v1/benefits/definitions?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/benefits/definitions",
        "per_page": 15,
        "to": 3,
        "total": 3
    }
}
```

This API lets you list all benefit definitions.

### HTTP Request

`GET /api/v1/benefits/definitions`



## Retrieve a benefit definition

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "minima",
        "handle": "dolorem-veritatis-quo-exercitationem",
        "period": 13,
        "description": "Quos aliquam sunt deserunt nobis blanditiis culpa temporibus. Et quidem non quis voluptatum blanditiis sunt eum laudantium. Maxime alias officiis nihil culpa.",
        "notes": "Perspiciatis laborum sed quis aut iure. Ratione libero omnis inventore libero. Quisquam exercitationem exercitationem debitis autem aut.",
        "max_redemptions": 667401,
        "is_extendable": false,
        "is_reassignable": false,
        "tags": [],
        "created_at": "2018-01-31 00:41:16",
        "updated_at": "2018-01-31 00:41:16"
    }
}
```

This API lets you retrieve a single benefit definition.

### HTTP Request

`GET /api/v1/benefits/definitions/{benefitDefinition}`



## Update a benefit definition

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "Birthday benefit",
        "handle": "dolorem-veritatis-quo-exercitationem",
        "period": 30,
        "description": "...",
        "notes": "xxx",
        "max_redemptions": 1,
        "is_extendable": false,
        "is_reassignable": false,
        "tags": [],
        "created_at": "2018-01-31 00:41:16",
        "updated_at": "2018-02-02 04:45:55"
    }
}
```

> JSON Request Example:
                
```json
{
  "name": "Birthday benefit",
  "period": 30,
  "description": "...",
  "notes": "xxx",
  "is_extendable": false,
  "max_redemptions": 1
}
```

This API lets you update a benefit definition.

### HTTP Request

`PUT /api/v1/benefits/definitions/{benefitDefinition}`

### Request Attributes
| Attribute       | Type                             |
|-----------------|----------------------------------|
| name            | `sometimes` `required` `string`  |
| description     | `sometimes` `nullable` `string`  |
| notes           | `sometimes` `nullable` `string`              |
| period          | `sometimes` `required` `integer` |
| is_extendable   | `sometimes` `nullable` `boolean` |
| max_redemptions | `sometimes` `nullable` `integer` |
| tags            | `sometimes` `required` `array`   |
| tags.*.id       | `required` `exists`              |




## Delete a benefit definition

This API lets you delete a benefit definition.

### HTTP Request

`DELETE /api/v1/benefits/definitions/{benefitDefinition}`

