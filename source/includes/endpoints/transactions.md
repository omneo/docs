## Transactions

This API allows you to create, read, update and delete transactions.

### Transaction Properties

| Property     | Description                                  | 
|---------------|----------------------------------------------|
| id            | ID of the transaction.                       |
| external_id | External ID of the transaction.                       |
| redemption_id | Associated redemption ID.                       |
| profile_id    | The profile associate with this transaction  |
| location_id   | The location that this transaction happened  |
| currency      | The currency this transaction use            |
| total         | The total value of the transaction           |
| rounding      | The value rounded                            |
| tender        | ...                                          |
| margin        | The margin of this transaction               |
| ereceipt      | Whether this transaction has e-receipt       |
| ereciept_text | The e-receipt content for this transaction   |
| deliver_at    | Transaction delivery time                    |
| transacted_at | Transaction happen time                      |





### Create a transaction

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "external_id": "4442-4421-4555-9828",
        "redemption": null,
        "location": null,
        "currency": "AUD",
        "total": 199.56,
        "systems": null,
        "rounding": 199.6,
        "tender": null,
        "margin": 0.06,
        "ereceipt": false,
        "ereciept_text": null,
        "deliver_at": "2018-01-01 12:00:00",
        "transacted_at": "2018-01-01 12:00:00",
        "tags": [],
        "items": [
            {
                "id": 13,
                "name": "Brown Dress Shoes",
                "quantity": 2,
                "price_current": 23,
                "price_sell": 23,
                "price_original": 23,
                "price_margin": 0,
                "product": {
                    "id": 1,
                    "title": "Brown Dress Shoes",
                    "description": "Dress shoes that suit any occasion.",
                    "position": 4,
                    "price": 52.67,
                    "price_discounted": 79.53,
                    "price_comparison": 5.54,
                    "price_cost": 78.07,
                    "available_quantity": 0,
                    "tags": [],
                    "options": [],
                    "created_at": "2018-01-31 00:41:16",
                    "updated_at": "2018-01-31 00:41:16"
                },
                "created_at": "2018-02-02 03:39:06",
                "updated_at": "2018-02-02 03:39:06"
            }
        ],
        "created_at": "2018-02-02 03:39:06",
        "updated_at": "2018-02-02 03:39:06"
    }
}
```

> JSON Request Example:

```json
{
  "external_id": "4442-4421-4555-9828",
  "redemption_id": "1",
  "profile_id": 1,
  "location_id": 1,
  "currency": "AU",
  "total": 199.56,
  "rounding": 199.6,
  "margin": 0.06,
  "ereceipt": false,
  "ereciept_text": null,
  "deliver_at": "2018-01-01 12:00:00",
  "transacted_at": "2018-01-01 12:00:00",
  "items": [
    {
        "name": "My Transaction Item",
        "quantity": 2,
        "price_current": 23,
        "price_sell": 23,
        "price_original": 23,
        "price_margin": 0,
        "product_id": 1
    }
  ]
}
```


This API allows you to create a transaction.

#### HTTP Request

`POST /api/v1/transactions`

#### Request Properties

| Property     | Type                                 |
|---------------|--------------------------------------|
| profile_id    | `required` `integer` `exists`        |
| redemption_id    | `sometimes` `integer` `exists`    |
| external_id    | `sometimes` `nullable` `string`    |
| location_id   | `nullable` `integer` `exists`        |
| currency      | `nullable` `string`                  |
| total         | `required` `numeric`                 |
| rounding      | `nullable` `numeric`                 |
| tender        | `nullable` `numeric`                 |
| margin        | `nullable` `numeric`                 |
| ereceipt      | `nullable` `boolean`                 |
| ereciept_text | `nullable` `string`                  |
| deliver_at    | `nullable` `date_format:Y-m-d H:i:s` |
| transacted_at | `required` `date_format:Y-m-d H:i:s` |
| items         | `sometimes` `required` `array`       |
| tags          | `sometimes` `required` `array`       |
| tags.*.id     | `required` `exists`                  |
| systems       | `sometimes` `required` `array`       |
| systems.*.id  | `required` `exists`                  |




### List all Transactions

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "profile": null,
            "location": null,
            "redemption": null,
            "currency": "AUD",
            "total": 143.53,
            "tags": [],
            "systems": [],
            "rounding": 144.51,
            "tender": 100,
            "margin": 101.1,
            "ereceipt": false,
            "ereciept_text": null,
            "deliver_at": null,
            "transacted_at": "2018-03-11 14:13:07",
            "items": [
                {
                    "id": 12,
                    "name": "My Transaction Item",
                    "quantity": 1,
                    "price_current": 10,
                    "price_sell": 10,
                    "price_original": 10,
                    "price_margin": 0,
                    "product": {
                        "id": 2,
                        "title": "My Product",
                        "position": 6,
                        "price": 78.41,
                        "price_discounted": 145.19,
                        "price_comparison": 36.03,
                        "price_cost": 46.86,
                        "available_quantity": 4,
                        "tags": [],
                        "systems": [],
                        "channels": [],
                        "options": [],
                        "created_at": "2018-01-31 00:41:16",
                        "updated_at": "2018-01-31 00:41:16"
                    },
                    "created_at": "2018-02-02 01:16:16",
                    "updated_at": "2018-02-02 01:17:29"
                }
            ],
            "created_at": "2018-02-01 02:47:31",
            "updated_at": "2018-02-01 02:47:31"
        }
    ]
}
```

This API lets you list all transactions.

#### HTTP Request

`GET /api/v1/transactions`



### Retrieve a transaction

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "profile": null,
        "location": null,
        "redemption": null,
        "currency": "AUD",
        "total": 143.53,
        "tags": [],
        "systems": [],
        "rounding": 144.51,
        "tender": 100,
        "margin": 101.1,
        "ereceipt": false,
        "ereciept_text": null,
        "deliver_at": null,
        "transacted_at": "2018-03-11 14:13:07",
        "items": [
            {
                "id": 12,
                "name": "My Transaction Item",
                "quantity": 1,
                "price_current": 10,
                "price_sell": 10,
                "price_original": 10,
                "price_margin": 0,
                "product": {
                    "id": 2,
                    "title": "My Product",
                    "position": 6,
                    "price": 78.41,
                    "price_discounted": 145.19,
                    "price_comparison": 36.03,
                    "price_cost": 46.86,
                    "available_quantity": 4,
                    "tags": [],
                    "systems": [],
                    "channels": [],
                    "options": [],
                    "created_at": "2018-01-31 00:41:16",
                    "updated_at": "2018-01-31 00:41:16"
                },
                "created_at": "2018-02-02 01:16:16",
                "updated_at": "2018-02-02 01:17:29"
            }
        ],
        "created_at": "2018-02-01 02:47:31",
        "updated_at": "2018-02-01 02:47:31"
    }
}
```

This API lets you retrieve a single transaction.

#### HTTP Request

`GET /api/v1/transactions/{transaction}`



### Update a transaction

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "profile": null,
        "location": null,
        "redemption": null,
        "currency": "AUD",
        "total": 143.53,
        "tags": [],
        "systems": [],
        "rounding": 144.51,
        "tender": 100,
        "margin": 101.1,
        "ereceipt": false,
        "ereciept_text": null,
        "deliver_at": null,
        "transacted_at": "2018-03-11 14:13:07",
        "items": [
            {
                "id": 12,
                "name": "My Transaction Item",
                "quantity": 1,
                "price_current": 10,
                "price_sell": 10,
                "price_original": 10,
                "price_margin": 0,
                "product": {
                    "id": 2,
                    "title": "My Product",
                    "position": 6,
                    "price": 78.41,
                    "price_discounted": 145.19,
                    "price_comparison": 36.03,
                    "price_cost": 46.86,
                    "available_quantity": 4,
                    "tags": [],
                    "systems": [],
                    "channels": [],
                    "options": [],
                    "created_at": "2018-01-31 00:41:16",
                    "updated_at": "2018-01-31 00:41:16"
                },
                "created_at": "2018-02-02 01:16:16",
                "updated_at": "2018-02-02 01:17:29"
            }
        ],
        "created_at": "2018-02-01 02:47:31",
        "updated_at": "2018-02-03 02:47:31"
    }
}
```

> JSON Request Example:
                
```json
{
    "profile_id": 1,
    "total": 100.92,
    "currency": "AUD"
}
```

This API lets you update a transaction.

#### HTTP Request

`PUT /api/v1/transactions/{transaction}`

#### Request Properties

| Property     | Type                                             |
|---------------|--------------------------------------------------|
| location_id   | `sometimes` `nullable` `integer` `exists`        |
| currency      | `sometimes` `nullable` `string`                  |
| external_id      | `sometimes` `nullable` `string`               |
| redemption_id      | `sometimes` `required` `exists`               |
| total         | `sometimes` `numeric`                            |
| rounding      | `sometimes` `nullable` `numeric`                 |
| tender        | `sometimes` `nullable` `numeric`                 |
| margin        | `sometimes` `nullable` `numeric`                 |
| ereceipt      | `sometimes` `nullable` `boolean`                 |
| ereciept_text | `sometimes` `nullable` `string`                  |
| deliver_at    | `sometimes` `nullable` `date_format:Y-m-d H:i:s` |
| transacted_at | `sometime` `date_format:Y-m-d H:i:s`             |
| tags          | `sometimes` `array`                              |
| tags.*.id     | `required` `exists`                              |
| systems       | `sometimes` `required` `array`                   |
| systems.*.id  | `required` `exists`                              |




### Delete a transaction

This API lets you delete a transaction.

#### HTTP Request

`DELETE /api/v1/transactions/{transaction}`

