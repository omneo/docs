# Products Variants

This API allows you to create, read, update and delete product variants.

## Product Variant Properties

| Property            | Description                           | 
|----------------------|---------------------------------------|
| product_id           | Product associated with this variant. |
| title                | Variant title                         |
| description          | Variant description                   |
| available_quantity   | The available quantity of the product.|
| price                | Price                                 |
| price_discounted     | Price discount                        |
| price_comparison     | Price comparison                      |
| price_cost           | Price cost                            |
| position             | The position of the product           |
| tags                 | Tags attached to this products        |
| options              | Options attached to this products     |






## Create a product variant

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "title": "Red Hat",
        "description": "Hat in red",
        "position": 1,
        "price": 29.99,
        "price_discounted": 5,
        "price_comparison": 0,
        "price_cost": 19.99,
        "available_quantity": 20,
        "tags": [
            {
                "id": 2,
                "handle": "bbb",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            }
        ],
        "options": [
            {
                "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                "value": "ut",
                "option_id": 3,
                "value_id": 1
            },
            {
                "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                "value": "deleniti",
                "option_id": 3,
                "value_id": 2
            }
        ],
        "created_at": "2018-02-02 00:44:37",
        "updated_at": "2018-02-02 00:44:37"
    }
}
```

This API allows you to create a variant for a product.

### HTTP Request

`POST /api/v1/products/{product}/variants`

### Request Properties

| Property            | Type                           | 
|----------------------|--------------------------------|
| title                | `required` `string`            |
| available_quantity   | `nullable` `integer`           |
| description          | `nullable` `string`            |
| price                | `required` `numeric`           |
| price_discounted     | `nullable` `numeric`           |
| price_comparison     | `nullable` `numeric`           |
| price_cost           | `nullable` `numeric`           |
| position             | `nullable` `integer`           |
| tags                 | `sometimes` `required` `array` |
| tags.*.id            | `required` `integer` `exists`  |
| options              | `sometimes` `required` `array` |
| options.*.option_id  | `required` `integer` `exists`  |
| options.*.value_id   | `required` `integer` `exists`  |



> JSON Request Example:
                
```json
{
  "title": "Red Hat",
  "available_quantity": 20,
  "description": "Hat in red",
  "price": 29.99,
  "price_discounted": 5,
  "price_comparison": 0,
  "price_cost": 19.99,
  "position": 1,
  "tags": [
    {
      "id": 1
    },
    {
      "id": 2
    }
  ],
  "options": [
    {
      "option_id": 1,
      "value_id":1
    },
    {
      "option_id": 2,
      "value_id":2
    }
  ]
}
```







## List all product variants

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 15,
            "title": "Red Hat II",
            "description": "Hat in red version II",
            "position": 1,
            "price": 39.99,
            "price_discounted": 5,
            "price_comparison": 0,
            "price_cost": 29.99,
            "available_quantity": 20,
            "tags": [
                {
                    "id": 2,
                    "handle": "bbb",
                    "created_at": "2018-01-01 00:00:00",
                    "updated_at": "2018-01-01 00:00:00"
                }
            ],
            "options": [
                {
                    "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                    "value": "ut",
                    "option_id": 3,
                    "value_id": 1
                },
                {
                    "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                    "value": "deleniti",
                    "option_id": 3,
                    "value_id": 2
                }
            ],
            "created_at": "2018-02-01 00:18:00",
            "updated_at": "2018-02-01 00:58:32"
        },
        {
            "id": 17,
            "title": "Red Hat",
            "description": "Hat in red",
            "position": 1,
            "price": 29.99,
            "price_discounted": 5,
            "price_comparison": 0,
            "price_cost": 19.99,
            "available_quantity": 20,
            "tags": [],
            "options": [],
            "created_at": "2018-02-02 00:33:00",
            "updated_at": "2018-02-02 00:33:00"
        },
        {
            "id": 18,
            "title": "Red Hat",
            "description": "Hat in red",
            "position": 1,
            "price": 29.99,
            "price_discounted": 5,
            "price_comparison": 0,
            "price_cost": 19.99,
            "available_quantity": 20,
            "tags": [],
            "options": [],
            "created_at": "2018-02-02 00:33:21",
            "updated_at": "2018-02-02 00:33:21"
        },
        {
            "id": 19,
            "title": "Red Hat",
            "description": "Hat in red",
            "position": 1,
            "price": 29.99,
            "price_discounted": 5,
            "price_comparison": 0,
            "price_cost": 19.99,
            "available_quantity": 20,
            "tags": [],
            "options": [],
            "created_at": "2018-02-02 00:44:29",
            "updated_at": "2018-02-02 00:44:29"
        },
        {
            "id": 20,
            "title": "Red Hat",
            "description": "Hat in red",
            "position": 1,
            "price": 29.99,
            "price_discounted": 5,
            "price_comparison": 0,
            "price_cost": 19.99,
            "available_quantity": 20,
            "tags": [
                {
                    "id": 2,
                    "handle": "bbb",
                    "created_at": "2018-01-01 00:00:00",
                    "updated_at": "2018-01-01 00:00:00"
                }
            ],
            "options": [
                {
                    "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                    "value": "ut",
                    "option_id": 3,
                    "value_id": 1
                },
                {
                    "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                    "value": "deleniti",
                    "option_id": 3,
                    "value_id": 2
                }
            ],
            "created_at": "2018-02-02 00:44:37",
            "updated_at": "2018-02-02 00:44:37"
        }
    ]
}
```

This API lets you list all products.

### HTTP Request

`GET /api/v1/products/{product}/variants`







## Retrieve a product variant

> JSON Response Example:
                
```json
{
    "data": {
        "id": 15,
        "title": "Red Hat II",
        "description": "Hat in red version II",
        "position": 1,
        "price": 39.99,
        "price_discounted": 5,
        "price_comparison": 0,
        "price_cost": 29.99,
        "available_quantity": 20,
        "tags": [
            {
                "id": 2,
                "handle": "bbb",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            }
        ],
        "options": [
            {
                "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                "value": "ut",
                "option_id": 3,
                "value_id": 1
            },
            {
                "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                "value": "deleniti",
                "option_id": 3,
                "value_id": 2
            }
        ],
        "created_at": "2018-02-01 00:18:00",
        "updated_at": "2018-02-01 00:58:32"
    }
}
```

This API lets you retrieve a single product variant.

### HTTP Request

`GET /api/v1/products/{product}/variants/{variant}`







## Update a product variant

> JSON Response Example:
                
```json
{
    "data": {
        "id": 15,
        "title": "Red Hat IIs",
        "description": "Hat in red version II",
        "position": 1,
        "price": 39.99,
        "price_discounted": 5,
        "price_comparison": 0,
        "price_cost": 29.99,
        "available_quantity": 20,
        "tags": [
            {
                "id": 2,
                "handle": "bbb",
                "created_at": "2018-01-01 00:00:00",
                "updated_at": "2018-01-01 00:00:00"
            }
        ],
        "options": [
            {
                "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                "value": "ut",
                "option_id": 3,
                "value_id": 1
            },
            {
                "handle": "libero-iure-nisi-est-quisquam-dolores-in",
                "value": "deleniti",
                "option_id": 3,
                "value_id": 2
            }
        ],
        "created_at": "2018-02-01 00:18:00",
        "updated_at": "2018-02-02 00:50:05"
    }
}
```

> JSON Request Example:
                
```json
{
  "title": "Red Hat IIs",
  "available_quantity": 21,
  "description": "Hat in red version II",
  "price": 39.99,
  "price_discounted": 5,
  "price_comparison": 0,
  "price_cost": 29.99,
  "position": 1,
  "tags": [
    {
      "id": 2
    }
  ],
  "options": [
    {
      "option_id": 1,
      "value_id":1
    },
    {
      "option_id": 2,
      "value_id":2
    }
  ]
}
```

This API lets you update a product variant.

### HTTP Request

`PUT /api/v1/products/{products}/variants/{variant}`

### Request Properties

| Property            | Type                             |   
|----------------------|----------------------------------|
| title                | `sometimes` `required` `string`  |
| available_quantity   | `sometimes` `nullable` `integer` |
| description          | `sometimes` `nullable` `string`  |
| price                | `sometimes` `numeric`            |
| price_discounted     | `sometimes` `nullable` `numeric` |
| price_comparison     | `sometimes` `nullable` `numeric` |
| price_cost           | `sometimes` `nullable` `numeric` |
| position             | `nullable` `integer`             |
| tags                 | `sometimes` `required` `array`   |
| tags.*.id            | `required` `integer` `exists`    |
| options              | `sometimes` `required` `array`   |
| options.*.option_id  | `required` `integer` `exists`    |
| options.*.value_id   | `required` `integer` `exists`    |




## Delete a product

This API lets you delete a product variant.

### HTTP Request

`DELETE /api/v1/products/{product}/variants/{variant}`

