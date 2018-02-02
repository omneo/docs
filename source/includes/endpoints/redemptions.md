# Redemptions

This API allows you to redeem rewards or a benefit .

## Redemption Attributes

| Attribute       | Description                                          |
|-----------------|------------------------------------------------------|
| id              | The ID of the redemption                             |
| transaction_id  | The transaction associated with the redemption       |
| profile_id      | The profile associated with the redemption           |
| redeemable_id   | The benefit or reward associated with the redemption |
| redeemable_type | Either benefit or reward                             |
| location_id     | The location associated with the redemption          |
| value           | The value it redeemed                                |




## List all profile redemptions

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 4,
            "transaction": "{...}",
            "subject_type": "benefit",
            "subject": {
                "id": 1,
                "expires_at": "2001-07-22 18:32:31",
                "issued_at": "2001-07-09 18:32:31",
                "is_expired": true,
                "definition": {
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
                },
                "created_at": "2018-01-31 00:41:16",
                "updated_at": "2018-01-31 00:41:16"
            },
            "value": null,
            "created_at": "2018-01-01 00:00:00",
            "updated_at": "2018-01-01 00:00:00"
        }
    ]
}
```

This API lets you list all profile redemptions.

### HTTP Request

`GET /api/v1/profiles/{profile}/redemptions`



## Retrieve a profile redemption

> JSON Response Example:
                
```json
{
    "data": {
        "id": 4,
        "transaction": "{...}",
        "subject_type": "benefit",
        "subject": {
            "id": 1,
            "expires_at": "2001-07-22 18:32:31",
            "issued_at": "2001-07-09 18:32:31",
            "is_expired": true,
            "definition": {
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
            },
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-01-31 00:41:16"
        },
        "value": null,
        "created_at": "2018-01-01 00:00:00",
        "updated_at": "2018-01-01 00:00:00"
    }
}
```

This API lets you retrieve a single reward definition.

### HTTP Request

`GET /api/v1/profiles/{profile}/redemptions/{redemption}`









## Redeem a reward

> JSON Response Example:
                
```json
{
    "data": {
        "total_redeemed": 200,
        "balance": 50
    }
}
```

> JSON Request Example:

```json
{
  "amount":200,
  "transaction_id":1
}
```


This API allows you to redeem rewards.

### HTTP Request

`POST /api/v1/profiles/{profile}/rewards/redeem`

### Request Attributes
| Attribute      | Type                                       |
|----------------|--------------------------------------------|
| transaction_id | `required` `exists`                        |
| amount         | `required` `numeric` Should greater than 0 |



## Redeem a benefit

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "transaction": {
            "id": 1,
            "profile":"{...}",
            "location": null,
            "currency": "SAPIENTE",
            "total": 79.93,
            "systems": [],
            "rounding": 34.07,
            "tender": "amet",
            "margin": 63.35,
            "ereceipt": false,
            "ereciept_text": null,
            "deliver_at": "1978-10-03 03:09:40",
            "transacted_at": "1976-11-30 22:21:39",
            "tags": [],
            "items": [],
            "created_at": "2018-02-02 05:58:02",
            "updated_at": "2018-02-02 05:58:02"
        },
        "subject_type": "benefit",
        "subject": {
            "id": 1,
            "expires_at": "2018-02-16 05:58:02",
            "issued_at": "2018-02-02 05:58:02",
            "is_expired": false,
            "definition": {
                "id": 1,
                "name": "cumque",
                "handle": "rerum-iusto-quae-et",
                "period": 14,
                "description": "Ea commodi nobis rerum rem sunt dolore. Et voluptate ea adipisci voluptatum. Vel et iste culpa aut sunt consequatur.",
                "notes": "Nulla et eos non aliquid praesentium sunt architecto qui. Nihil quis est temporibus corrupti minima. Sint sed explicabo sit fugit fugit repudiandae.",
                "max_redemptions": 7,
                "is_extendable": false,
                "is_reassignable": false,
                "tags": [],
                "created_at": "2018-02-02 05:58:02",
                "updated_at": "2018-02-02 05:58:02"
            },
            "created_at": "2018-02-02 05:58:02",
            "updated_at": "2018-02-02 05:58:02"
        },
        "value": null,
        "created_at": "2018-02-02 05:59:58",
        "updated_at": "2018-02-02 05:59:58"
    }
}
```

> JSON Request Example:

```json
{
  "transaction_id":1
}
```


This API allows you to redeem a benefit.

### HTTP Request

`POST /api/v1/profiles/{profile}/benefits/{benefit}/redeem`

### Request Attributes
| Attribute      | Type                                        |
|----------------|---------------------------------------------|
| transaction_id | `sometimes` `required` `integer` `exists`   |

