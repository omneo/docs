# Transactions Items

This API allows you to create, read, update and delete transaction items.


## Transaction Item Properties

| Property      | Description                               |
|----------------|-------------------------------------------|
| id             | The ID of the transaction item            |
| name           | The name of the transaction item          |
| transaction_id | The transaction associated with this item |
| product_id     | The product associated with this item     |
| quantity       | The number of the item                    |
| price_current  | Item's current price                      |
| price_sell     | Item's sell price                         |
| price_original | Item's original price                     |
| price_margin   | Item's price margin                       |







## Create a transaction item

> JSON Response Example:
                
```json
{
    "data": {
        "id": 12,
        "name": "transaction name",
        "quantity": 2,
        "price_current": 20,
        "price_sell": 20,
        "price_original": 20,
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
        "created_at": "2018-02-02 01:16:16",
        "updated_at": "2018-02-02 01:16:16"
    }
}
```
> JSON Request Example:
                
```json
{
  "name" : "transaction name",
  "quantity" : 2,
  "price_current" : 20,
  "price_sell" : 20,
  "price_original" : 20,
  "price_margin" : 0,
  "product_id" : 1
}
```

This API allows you to create a transaction item.

### HTTP Request

`POST /api/v1/transactions/{transaction}/items`

### Request Properties

| Property      | Type                          |
|----------------|-------------------------------|
| name           | `required` `string`           |
| quantity       | `required` `integer`          |
| price_current  | `required` `numeric`          |
| price_sell     | `required` `numeric`          |
| price_original | `required` `numeric`          |
| price_margin   | `required` `numeric`          |
| product_id     | `required` `integer` `exists` |







## List all transaction items

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 8,
            "name": "Iste perspiciatis quisquam.",
            "quantity": 76717,
            "price_current": 78.29,
            "price_sell": 18.91,
            "price_original": 113.21,
            "price_margin": 10.93,
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
            "created_at": "2018-02-01 02:47:31",
            "updated_at": "2018-02-01 02:47:31"
        },
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
    ]
}
```

This API lets you list all transaction items.

### HTTP Request

`GET /api/v1/transactions/{transaction}/items`






## Retrieve a transaction item

> JSON Response Example:
                
```json
{
    "data": {
        "id": 8,
        "name": "Iste perspiciatis quisquam.",
        "quantity": 76717,
        "price_current": 78.29,
        "price_sell": 18.91,
        "price_original": 113.21,
        "price_margin": 10.93,
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
        "created_at": "2018-02-01 02:47:31",
        "updated_at": "2018-02-01 02:47:31"
    }
}
```

This API lets you retrieve a single transaction item.

### HTTP Request

`GET /api/v1/transactions/{transaction}/items/{item}`







## Update a transaction item

> JSON Response Example:
                
```json
{
    "data": {
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
}
```


> JSON Request Example:
                
```json
{
  "name" : "transaction name II",
  "quantity" : 1,
  "price_current" : 10,
  "price_sell" : 10,
  "price_original" : 10,
  "price_margin" : 0,
  "product_id" : 2
}
```

This API lets you update a transaction item.

### HTTP Request

`PUT /api/v1/transactions/{transaction}/items/{item}`

### Request Properties

| Property      | Type                                      |
|----------------|-------------------------------------------|
| name           | `sometimes` `required` `string`           |
| quantity       | `sometimes` `required` `integer`          |
| price_current  | `sometimes` `required` `numeric`          |
| price_sell     | `sometimes` `required` `numeric`          |
| price_original | `sometimes` `nullable` `numeric`          |
| price_margin   | `sometimes` `nullable` `numeric`          |
| product_id     | `sometimes` `required` `integer` `exists` |
| tags           | `sometimes` `required` `array`            |
| tags.*.id      | `required` `exists`                       |





## Delete a transaction item

This API lets you delete a transaction item.

### HTTP Request

`DELETE /api/v1/transactions/{transaction}/items/{item}`

