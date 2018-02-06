# Products

This API allows you to create, read, update and delete products.

## Product Properties

| Property   | Description                       | 
|-------------|-----------------------------------|
| id          | ID of the product.                |
| title       | Title of the product.             |
| handle      | Unique handle for the product.    |
| external_id | External link.                    |
| status      | The status of the product.        |
| brand       | Product's brand.                  |
| description | Product's description.            |
| currency    | The currency of product's price.  |
| position    | The position of the product.      |
| tags        | Tags attaching to this products.  |
| options     | Options belong to this products.  |
| channels    | Channels this product has.        |
| systems     | Systems this product belongs to.  |






## Create a product

> JSON Response Example:
                
```json
{
    "data": {
        "id": 15,
        "external_id": null,
        "title": "Hat",
        "handle": "fashion-hat-22",
        "systems": [],
        "channels": [],
        "brand": "Mimco",
        "status": "rundown",
        "description": "Special design",
        "currency": null,
        "position": 1,
        "tags": [],
        "options": [],
        "variants": [
            {
                "id": 16,
                "title": "My Default Variant",
                "description": null,
                "position": 1,
                "price": 0,
                "price_discounted": null,
                "price_comparison": null,
                "price_cost": null,
                "available_quantity": null,
                "tags": [],
                "options": [],
                "created_at": "2018-02-01 08:12:19",
                "updated_at": "2018-02-01 08:12:19"
            }
        ],
        "created_at": "2018-02-01 08:12:19",
        "updated_at": "2018-02-01 08:12:19"
    }
}
```


This API allows you to create a product.

### HTTP Request

`POST /api/v1/products`

### Request Properties

| Property   | Type                                                                       |
|-------------|----------------------------------------------------------------------------|
| title       | `required`  `string`                                                       |
| handle      | `required`  `string` `unique`                                              |
| external_id | `nullable`  `string`                                                       |
| status      | `nullable`  `string`  `in: new,active,rundown,discontinued,ranged,deleted` |
| brand       | `required`  `string`    .                                      |
| description | `nullable`  `string`                                                       |
| currency    | `nullable`  `string`                                                       |
| position    | `sometimes` `integer`                                                    |
| tags        | `sometimes`  `array`                                              |
| options     | `sometimes`  `array`                                             |
| channels    | `sometimes`  `array`               |
| systems     | `sometimes`  `array`.                |




## List all Products

> JSON Response Example:
                
```json
{
  "data": [
    {
      "id": 1,
      "external_id": "87f50fcc-5ed6-3125-9f7a-a30c5c82c98f",
      "title": "Labore omnis nobis dolorum eius.",
      "handle": "ea-velit-quod-occaecati-suscipit",
      "systems": [],
      "channels": [],
      "brand": "Roberts, Ernser and Jacobi",
      "status": "ranged",
      "description": "<html><head><title>Rerum doloremque ut.</title></head><body><form action=\"example.org\" method=\"POST\"><label for=\"username\">nostrum</label><input type=\"text\" id=\"username\"><label for=\"password\">nisi</label><input type=\"password\" id=\"password\"></form><div id=\"86231\"><ul><li>Assumenda.</li><li>Iure repudiandae.</li></ul></div></body></html>\n",
      "currency": "AUD",
      "position": 0,
      "tags": [],
      "options": [],
      "variants": [],
      "created_at": "2018-02-01 01:47:01",
      "updated_at": "2018-02-01 01:47:01"
    },
    {
      "id": 2,
      "external_id": "22739e91-7695-316b-9e51-8d6daf27a25a",
      "title": "In quia molestiae.",
      "handle": "non-dolores-at-blanditiis",
      "systems": [],
      "channels": [],
      "brand": "Murphy-Harvey",
      "status": "ranged",
      "description": "<html><head><title>Blanditiis eaque quas numquam ipsa itaque nemo cum.</title></head><body><form action=\"example.net\" method=\"POST\"><label for=\"username\">quasi</label><input type=\"text\" id=\"username\"><label for=\"password\">sed</label><input type=\"password\" id=\"password\"></form><div id=\"72005\"><div class=\"est\"></div><div id=\"69875\"></div><div id=\"20314\"></div><div class=\"facere\"></div></div><div id=\"55062\"><div id=\"43572\"></div><div id=\"42659\"></div></div><div class=\"debitis\"></div></body></html>\n",
      "currency": "AUD",
      "position": 1,
      "tags": [],
      "options": [],
      "variants": [
        {
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
        }
      ],
      "created_at": "2018-01-31 00:41:16",
      "updated_at": "2018-01-31 00:41:16"
    }
  ],
  "links": {
    "first": "http://omneo-api.dev/api/v1/products?page=1",
    "last": "http://omneo-api.dev/api/v1/products?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "http://omneo-api.dev/api/v1/products",
    "per_page": 15,
    "to": 15,
    "total": 15
  }
}
```

This API lets you list all products.

### HTTP Request

`GET /api/v1/products`



## Retrieve a product

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "external_id": "22739e91-7695-316b-9e51-8d6daf27a25a",
        "title": "In quia molestiae.",
        "handle": "non-dolores-at-blanditiis",
        "systems": [],
        "channels": [],
        "brand": "Murphy-Harvey",
        "status": "ranged",
        "description": "<html><head><title>Blanditiis eaque quas numquam ipsa itaque nemo cum.</title></head><body><form action=\"example.net\" method=\"POST\"><label for=\"username\">quasi</label><input type=\"text\" id=\"username\"><label for=\"password\">sed</label><input type=\"password\" id=\"password\"></form><div id=\"72005\"><div class=\"est\"></div><div id=\"69875\"></div><div id=\"20314\"></div><div class=\"facere\"></div></div><div id=\"55062\"><div id=\"43572\"></div><div id=\"42659\"></div></div><div class=\"debitis\"></div></body></html>\n",
        "currency": "AUD",
        "position": 1,
        "tags": [],
        "options": [],
        "variants": [
            {
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
            }
        ],
        "created_at": "2018-01-31 00:41:16",
        "updated_at": "2018-01-31 00:41:16"
    }
}
```

This API lets you retrieve a single profile.

### HTTP Request

`GET /api/v1/products/{product}`



## Update a product

> JSON Response Example:
                
```json
{
  "title": "Hat Red"
}
```

This API lets you update a profile.

### HTTP Request

`PUT /api/v1/products/{products}`

### Request Properties

| Property   | Type                                                                       |
|-------------|----------------------------------------------------------------------------|
| title       | `required`  `string`                                                       |
| handle      | `required`  `string` `unique`                                              |
| external_id | `nullable`  `string`                                                       |
| status      | `nullable`  `string`  `in: new,active,rundown,discontinued,ranged,deleted` |
| brand       | `required`  `string`                                                       |
| description | `nullable`  `string`                                                       |
| currency    | `nullable`  `string`                                                       |
| position    | Default to 1. `integer`                                                    |
| tags        | `nullable`  Must be an array.                                              |
| options     | `nullable`  Must be an array.                                              |
| channels    | `nullable`  Must be an array. Must exists on channel table.                |
| systems     | `nullable`  Must be an array. Must exists on systems table.                |





## Delete a product

This API lets you delete a product.

### HTTP Request

`DELETE /api/v1/products/{product}`

