# Categories

## Get All Categories

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories"
```

> The above command returns JSON structured like this:

```json
{
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories"
	},
	"data": [{
		"type": "categories",
		"id": "1",
		"attributes": {
			"name": "Chasse"
		},
		"relationships": {
			"menus": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories/1/menus"
				}
			}
		}
	}, {
		"type": "categories",
		"id": "2",
		"attributes": {
			"name": "Végétarien"
		},
		"relationships": {
			"menus": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories/2/menus"
				}
			}
		}
	}]
}
```

This endpoint retrieves all menu categories.

### HTTP Request

`GET /api/beta/categories`


## Get a Specific Category

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories/1"
```

> The above command returns JSON structured like this:

```json
{
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories/1"
	},
	"data": {
		"type": "categories",
		"id": "1",
		"attributes": {
			"name": "Chasse"
		},
		"relationships": {
			"menus": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories/1/menus"
				}
			}
		}
	}
}
```

This endpoint retrieves a specific menu category.

### HTTP Request

`GET /api/beta/categories/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the menu category to retrieve

