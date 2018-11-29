# Dishes

## Get a Specific Dish

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/dishes/1"
```

> The above command returns JSON structured like this:

```json
{
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/dishes/1"
	},
	"data": {
		"type": "dishes",
		"id": "1",
		"attributes": {
			"name": "Lasagne",
			"type": "main"
		},
		"relationships": {
			"menus": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/dishes/1/menu"
				},
				"data": {
					"type": "menus",
					"id": "1"
				}
			}
		}
	},
	"included": [{
		"type": "menus",
		"id": "1",
		"attributes": {
			"name": "Menu italien",
			"price": 11.95,
			"start": "2018-11-05T00:00:00Z",
			"end": "2018-11-09T14:00:00Z",
			"active": true
		},
		"relationships": {
			"restaurant": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1/restaurant"
				},
				"data": {
					"type": "restaurants",
					"id": "1"
				}
			},
			"category": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1/category"
				},
				"data": {
					"type": "categories",
					"id": "1"
				}
			},
			"dishes": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1/dishes"
				},
				"data": [{
						"type": "dishes",
						"id": "1"
					},
					{
						"type": "dishes",
						"id": "2"
					},
					{
						"type": "dishes",
						"id": "3"
					}
				]
			}
		}
	}]
}
```

This endpoint retrieves a specific dish.

### HTTP Request

`GET /api/beta/dishes/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the dish to retrieve

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
include | ``null`` | Comma separated list of relationships to include in the response document. Must be ``null`` or ``menus``.
