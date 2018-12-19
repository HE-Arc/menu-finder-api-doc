# Categories

## Get All Categories

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories"
```

> The above command returns JSON structured like this:

```json
{
	"data": [{
		"type": "categories",
		"id": "1",
		"attributes": {
			"name": "Chasse"
		},
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/categories/1"
		}
	}, {
		"type": "categories",
		"id": "2",
		"attributes": {
			"name": "Végétarien"
		},
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/categories/2"
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
	"data": {
		"type": "categories",
		"id": "1",
		"attributes": {
			"name": "Chasse"
		}
	},
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories/1"
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

