# Ledgers

This API allows you to read ledgers.

## Role Attributes

| Attribute       | Description                                                | 
|-----------------|------------------------------------------------------------|
| id              | ID of the role                                             |
| profile_id      | The name of the role                                       |
| ledgerable_id   | The ID of the subject                                      |
| ledgerable_type | The type of the subject                                    |
| description     | Description for this ledger                                |
| dollar_value    | Amount subject(transacted/reward/point) amount issued      |
| dollar_balance  | The profile's reward balance after this ledger implemented |
| point_value     | Amount of points issued or redeemed                        |
| point_balance   | The profile's reward balance after this ledger implemented |


## List all ledgers for a profile

> JSON Response Example:
                
```json
{
  "data": [
    {
      "id": 1,
      "profile": {...},
      "ledgerable_type": "transaction",
      "ledgerable_subject": {
        "id": 1,
        "profile_id": 5,
        "location_id": null,
        "currency": "QUAERAT",
        "total": 124.05,
        "rounding": 5.54,
        "tender": "ab",
        "margin": 54.94,
        "ereceipt": true,
        "ereciept_text": null,
        "deliver_at": "1980-08-30 02:43:07",
        "transacted_at": "2008-11-02 14:34:11",
        "created_at": "2018-02-12 05:51:22",
        "updated_at": "2018-02-12 05:51:22"
      },
      "description": "Transaction",
      "dollar_value": "124.05",
      "dollar_balance": "0.00",
      "point_value": 0,
      "point_balance": 0
    }
  ]
}
```

This API lets you list all ledger for a profile.

### HTTP Request

`GET /api/v1/profiles/{profile}/ledgers`



## Retrieve a ledger for a profile

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "profile": {...},
        "ledgerable_type": "transaction",
        "ledgerable_subject": {
            "id": 1,
            "profile_id": 5,
            "location_id": null,
            "currency": "QUAERAT",
            "total": 124.05,
            "rounding": 5.54,
            "tender": "ab",
            "margin": 54.94,
            "ereceipt": true,
            "ereciept_text": null,
            "deliver_at": "1980-08-30 02:43:07",
            "transacted_at": "2008-11-02 14:34:11",
            "created_at": "2018-02-12 05:51:22",
            "updated_at": "2018-02-12 05:51:22"
        },
        "description": "Transaction",
        "dollar_value": "124.05",
        "dollar_balance": "0.00",
        "point_value": 0,
        "point_balance": 0
    }
}
```

This API lets you retrieve a single ledger for a profile.

### HTTP Request

`GET /api/v1/profiles/{profile}/ledgers/{ledger}`