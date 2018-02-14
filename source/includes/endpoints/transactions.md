## Transactions

This API allows you to create, read, update and delete transactions.

### Transaction Properties

| Property        | Description                                  | 
|-----------------|----------------------------------------------|
| id              | ID of the transaction.                       |
| profile_id      | The profile associate with this transaction  |
| location_id     | The location that this transaction happened  |
| currency        | The currency this transaction use            |
| currency_rate   | The currency convert rate                    |
| _total_converted| Calculated value (total * currency_rate)     |
| total           | The total value of the transaction           |
| rounding        | The value rounded                            |
| tender          | ...                                          |
| margin          | The margin of this transaction               |
| ereceipt        | Whether this transaction has e-receipt       |
| ereciept_text   | The e-receipt content for this transaction   |
| deliver_at      | Transaction delivery time                    |
| transacted_at   | Transaction happen time                      |





### Create a transaction

> JSON Response Example:
                
```json
{
    "data": {
        "id": 21,
        "profile": {...},
        "location": {...},
        "currency": "AU",
        "currency_rate": "1",
        "total": 199.56,
        " _total_converted": 199.56,
        "systems": [
            {
                "id": 1,
                "name": "ss",
                "handle": "ss",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            },
            {
                "id": 2,
                "name": "zz",
                "handle": "zz",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            }
        ],
        "rounding": 199.6,
        "tender": null,
        "margin": 0.06,
        "ereceipt": false,
        "ereciept_text": null,
        "deliver_at": "2018-01-01 12:00:00",
        "transacted_at": "2018-01-01 12:00:00",
        "tags": [
            {
                "id": 2,
                "handle": "bbb",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            }
        ],
        "items": [
            {
                "id": 13,
                "name": "item name",
                "quantity": 2,
                "price_current": 23,
                "price_sell": 23,
                "price_original": 23,
                "price_margin": 0,
                "product": {
                    "id": 1,
                    "title": "Animi ullam a.",
                    "description": "<html><head><title>Aliquam aut aut corporis.</title></head><body><form action=\"example.com\" method=\"POST\"><label for=\"username\">perferendis</label><input type=\"text\" id=\"username\"><label for=\"password\">quisquam</label><input type=\"password\" id=\"password\"></form><div id=\"11373\"><div id=\"88436\"><i>Cumque distinctio.</i><a href=\"example.org\">Qui commodi quia dolores.</a></div><div id=\"50741\"></div><div class=\"ducimus\">Est amet non sit perferendis consequatur est dignissimos.</div><div id=\"5308\"></div></div><div id=\"47976\"><ul><li>Blanditiis amet nulla sed esse.</li><li>Aut qui.</li></ul>Ducimus nisi nemo distinctio.</div><div class=\"praesentium\"><div id=\"46595\"></div><div id=\"67601\">Architecto aut et.<a href=\"example.net\">Qui fuga debitis odio sed illum molestiae iste in.</a><ul><li>Vitae dolores.</li><li>Corporis amet et.</li><li>Et nisi.</li><li>Omnis.</li><li>A voluptas.</li><li>Corporis molestias ut officia libero.</li><li>Voluptatem sed.</li><li>Laudantium nostrum facilis.</li><li>Ut est accusantium.</li></ul></div><div class=\"molestiae\"></div></div><div id=\"32617\"></div></body></html>\n",
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
  "profile_id": 1,
  "location_id": 1,
  "currency": "AU",
  "currency_rate": "1",
  "total": 199.56,
  "rounding": 199.6,
  "margin": 0.06,
  "ereceipt": false,
  "ereciept_text": null,
  "deliver_at": "2018-01-01 12:00:00",
  "transacted_at": "2018-01-01 12:00:00",
  "items": [
    {
      "name" : "item name",
      "quantity" : 2,
      "price_current" : 23,
      "price_sell" : 23,
      "price_original" : 23,
      "price_margin" : 0,
      "product_id" :1
    }
  ],
  "tags": [
    {
      "id": 2
    }
  ],
  "systems": [
    {
      "id": 1
    },
    {
      "id": 2
    }
  ]
}
```


This API allows you to create a transaction.

#### HTTP Request

`POST /api/v1/transactions`

#### Request Properties

| Property      | Type                                       |
|---------------|--------------------------------------------|
| profile_id    | `required` `integer` `exists`              |
| location_id   | `nullable` `integer` `exists`              |
| currency      | `nullable` `string` `exists:currencies,to` |
| currency_rate | `nullable` `numeric`                       |
| total         | `required` `numeric`                       |
| rounding      | `nullable` `numeric`                       |
| tender        | `nullable` `numeric`                       |
| margin        | `nullable` `numeric`                       |
| ereceipt      | `nullable` `boolean`                       |
| ereciept_text | `nullable` `string`                        |
| deliver_at    | `nullable` `date_format:Y-m-d H:i:s`       |
| transacted_at | `required` `date_format:Y-m-d H:i:s`       |
| items         | `sometimes` `required` `array`             |
| tags          | `sometimes` `required` `array`             |
| tags.*.id     | `required` `exists`                        |
| systems       | `sometimes` `required` `array`             |
| systems.*.id  | `required` `exists`                        |




### List all Transactions

> JSON Response Example:
                
```json
{
  "data": [
    {
      "id": 15,
      "profile": {
        "id": 27,
        "title": "Dr.",
        "first_name": "Geraldine",
        "last_name": "Cartwright",
        "full_name": "Geraldine Cartwright",
        "email": "littel.ardella@runolfsdottir.com",
        "mobile_phone": "0401 222 111",
        "mobile_phone_country": "AU",
        "mobile_phone_e164": "+61401222111",
        "home_phone": null,
        "home_phone_country": null,
        "work_phone": null,
        "work_phone_country": null,
        "address": null,
        "avatar_url": null,
        "company": null,
        "occupation": null,
        "birth_year": 1999,
        "birth_month": 6,
        "birth_day": 6,
        "addresses": [],
        "balance": {
          "rewards": 0,
          "points": null
        },
        "joined_location": null,
        "tags": [],
        "created_at": "2018-02-01 02:47:31",
        "updated_at": "2018-02-01 02:47:31"
      },
      "location": {},
      "currency": "MAXIME",
      "currency_rate": "1",     
      "total": 143.53,
      " _total_converted": 199.56,
      "systems": [],
      "rounding": 144.51,
      "tender": "et",
      "margin": 101.1,
      "ereceipt": false,
      "ereciept_text": null,
      "deliver_at": "1998-03-27 01:58:46",
      "transacted_at": "2006-03-11 14:13:07",
      "tags": [],
      "items": [
        {
          "id": 12,
          "name": "transaction name II",
          "quantity": 1,
          "price_current": 10,
          "price_sell": 10,
          "price_original": 10,
          "price_margin": 0,
          "product": {
            "id": 2,
            "title": "Qui earum dolores voluptates.",
            "description": "<html><head><title>Sit repellendus eaque autem at numquam deserunt.</title></head><body><form action=\"example.com\" method=\"POST\"><label for=\"username\">beatae</label><input type=\"text\" id=\"username\"><label for=\"password\">quis</label><input type=\"password\" id=\"password\"></form><div id=\"2368\"><div class=\"animi\"><i>Qui non quaerat.</i><ul><li>Temporibus rerum.</li></ul><span>Tenetur non tempore earum.</span></div><div id=\"40253\"></div><div class=\"sint\"></div></div><div id=\"57452\"></div></body></html>\n",
            "position": 6,
            "price": 78.41,
            "price_discounted": 145.19,
            "price_comparison": 36.03,
            "price_cost": 46.86,
            "available_quantity": 4,
            "tags": [],
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
  ],
  "links": {
    "first": "http://omneo-api.dev/api/v1/transactions?page=1",
    "last": "http://omneo-api.dev/api/v1/transactions?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "http://omneo-api.dev/api/v1/transactions",
    "per_page": 15,
    "to": 5,
    "total": 5
  }
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
        "id": 15,
        "profile": {
            "id": 27,
            "title": "Dr.",
            "first_name": "Geraldine",
            "last_name": "Cartwright",
            "full_name": "Geraldine Cartwright",
            "email": "littel.ardella@runolfsdottir.com",
            "mobile_phone": "0401 222 111",
            "mobile_phone_country": "AU",
            "mobile_phone_e164": "+61401222111",
            "home_phone": null,
            "home_phone_country": null,
            "work_phone": null,
            "work_phone_country": null,
            "address": null,
            "avatar_url": null,
            "company": null,
            "occupation": null,
            "birth_year": 1999,
            "birth_month": 6,
            "birth_day": 6,
            "addresses": [],
            "balance": {
                "rewards": 0,
                "points": null
            },
            "joined_location": null,
            "tags": [],
            "created_at": "2018-02-01 02:47:31",
            "updated_at": "2018-02-01 02:47:31"
        },
        "location": {},
        "currency": "MAXIME",
        "currency_rate": "1",
        "total": 143.53,
        " _total_converted": 199.56,
        "systems": [],
        "rounding": 144.51,
        "tender": "et",
        "margin": 101.1,
        "ereceipt": false,
        "ereciept_text": null,
        "deliver_at": "1998-03-27 01:58:46",
        "transacted_at": "2006-03-11 14:13:07",
        "tags": [],
        "items": [
            {
                "id": 12,
                "name": "transaction name II",
                "quantity": 1,
                "price_current": 10,
                "price_sell": 10,
                "price_original": 10,
                "price_margin": 0,
                "product": {
                    "id": 2,
                    "title": "Qui earum dolores voluptates.",
                    "description": "<html><head><title>Sit repellendus eaque autem at numquam deserunt.</title></head><body><form action=\"example.com\" method=\"POST\"><label for=\"username\">beatae</label><input type=\"text\" id=\"username\"><label for=\"password\">quis</label><input type=\"password\" id=\"password\"></form><div id=\"2368\"><div class=\"animi\"><i>Qui non quaerat.</i><ul><li>Temporibus rerum.</li></ul><span>Tenetur non tempore earum.</span></div><div id=\"40253\"></div><div class=\"sint\"></div></div><div id=\"57452\"></div></body></html>\n",
                    "position": 6,
                    "price": 78.41,
                    "price_discounted": 145.19,
                    "price_comparison": 36.03,
                    "price_cost": 46.86,
                    "available_quantity": 4,
                    "tags": [],
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
        "id": 19,
        "profile": {
            "id": 1,
            "title": "Mr.",
            "first_name": "Furman",
            "last_name": "Gerhold",
            "full_name": "Furman Gerhold",
            "email": "hartmann.melyssa@gmail.com",
            "mobile_phone": "0401 222 111",
            "mobile_phone_country": "AU",
            "mobile_phone_e164": "+61401222111",
            "home_phone": null,
            "home_phone_country": null,
            "work_phone": null,
            "work_phone_country": null,
            "address": null,
            "avatar_url": null,
            "company": null,
            "occupation": null,
            "birth_year": 1972,
            "birth_month": 0,
            "birth_day": 2,
            "addresses": [],
            "balance": {
                "rewards": 0,
                "points": null
            },
            "joined_location": null,
            "tags": [],
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-01-31 00:41:16"
        },
        "location": {},
        "currency": "NZ",
        "currency_rate": "1.08",
        "total": 199.56,
        " _total_converted": 199.56,
        "systems": [
            {
                "id": 1,
                "name": "ss",
                "handle": "ss",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            },
            {
                "id": 2,
                "name": "zz",
                "handle": "zz",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            }
        ],
        "rounding": 199.6,
        "tender": null,
        "margin": 0.06,
        "ereceipt": false,
        "ereciept_text": null,
        "deliver_at": "2018-01-01 12:00:00",
        "transacted_at": "2018-01-01 12:00:00",
        "tags": [
            {
                "id": 1,
                "handle": "aaa",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            },
            {
                "id": 2,
                "handle": "bbb",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            }
        ],
        "items": [
            {
                "id": 11,
                "name": "item name",
                "quantity": 2,
                "price_current": 23,
                "price_sell": 23,
                "price_original": 23,
                "price_margin": 0,
                "product": {
                    "id": 1,
                    "title": "Animi ullam a.",
                    "description": "<html><head><title>Aliquam aut aut corporis.</title></head><body><form action=\"example.com\" method=\"POST\"><label for=\"username\">perferendis</label><input type=\"text\" id=\"username\"><label for=\"password\">quisquam</label><input type=\"password\" id=\"password\"></form><div id=\"11373\"><div id=\"88436\"><i>Cumque distinctio.</i><a href=\"example.org\">Qui commodi quia dolores.</a></div><div id=\"50741\"></div><div class=\"ducimus\">Est amet non sit perferendis consequatur est dignissimos.</div><div id=\"5308\"></div></div><div id=\"47976\"><ul><li>Blanditiis amet nulla sed esse.</li><li>Aut qui.</li></ul>Ducimus nisi nemo distinctio.</div><div class=\"praesentium\"><div id=\"46595\"></div><div id=\"67601\">Architecto aut et.<a href=\"example.net\">Qui fuga debitis odio sed illum molestiae iste in.</a><ul><li>Vitae dolores.</li><li>Corporis amet et.</li><li>Et nisi.</li><li>Omnis.</li><li>A voluptas.</li><li>Corporis molestias ut officia libero.</li><li>Voluptatem sed.</li><li>Laudantium nostrum facilis.</li><li>Ut est accusantium.</li></ul></div><div class=\"molestiae\"></div></div><div id=\"32617\"></div></body></html>\n",
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
                "created_at": "2018-02-01 02:57:50",
                "updated_at": "2018-02-01 02:57:50"
            }
        ],
        "created_at": "2018-02-01 02:57:50",
        "updated_at": "2018-02-01 02:58:45"
    }
}
```

> JSON Request Example:
                
```json
{
  "currency": "NZ"
}
```

This API lets you update a transaction.

#### HTTP Request

`PUT /api/v1/transactions/{transaction}`

#### Request Properties

| Property      | Type                                                   |
|---------------|--------------------------------------------------------|
| location_id   | `sometimes` `nullable` `integer` `exists`              |
| currency      | `sometimes` `nullable` `string` `exists:currencies,to` |
| currency_rate | `sometimes` `nullable` `numeric`                       |
| total         | `sometimes` `numeric`                                  |
| rounding      | `sometimes` `nullable` `numeric`                       |
| tender        | `sometimes` `nullable` `numeric`                       |
| margin        | `sometimes` `nullable` `numeric`                       |
| ereceipt      | `sometimes` `nullable` `boolean`                       |
| ereciept_text | `sometimes` `nullable` `string`                        |
| deliver_at    | `sometimes` `nullable` `date_format:Y-m-d H:i:s`       |
| transacted_at | `sometime` `date_format:Y-m-d H:i:s`                   |
| tags          | `sometimes` `array`                                    |
| tags.*.id     | `required` `exists`                                    |
| systems       | `sometimes` `required` `array`                         |
| systems.*.id  | `required` `exists`                                    |




### Delete a transaction

This API lets you delete a transaction.

#### HTTP Request

`DELETE /api/v1/transactions/{transaction}`

