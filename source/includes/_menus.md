# Menus

## Get All Menus

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus"
```

> The above command returns JSON structured like this:

```json
{
	"data": [{
		"type": "menus",
		"id": "1",
		"attributes": {
			"name": "Menu italien",
			"price": 11.95,
			"start": "2018-12-19T00:00:00+00:00",
			"end": "2018-12-20T00:00:00+00:00",
			"active": true
		},
		"relationships": {
			"restaurant": {
				"data": {
					"type": "restaurants",
					"id": "1"
				},
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1/restaurant"
				}
			},
			"categories": {
				"data": [{
					"type": "categories",
					"id": "1"
				}, {
					"type": "categories",
					"id": "2"
				}],
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1/categories"
				}
			},
			"dishes": {
				"data": [{
					"type": "dishes",
					"id": "1"
				}, {
					"type": "dishes",
					"id": "2"
				}],
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1/dishes"
				}
			}
		},
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1"
		}
	}],
	"included": [{
		"type": "dishes",
		"id": "1",
		"attributes": {
			"name": "Lasagne",
			"dish-type": "main"
		}
	}, {
		"type": "dishes",
		"id": "2",
		"attributes": {
			"name": "Tiramisu",
			"dish-type": "dessert"
		}
	}]
}
```

This endpoint retrieves all menus or a list of menus filtered by a geospatial query according to the restaurant's position and a given radius.

Note that this endpoint will return a maximum of 50 menus and will include its related dishes by default (no need to provide ``include=dishes`` query parameter).

### HTTP Request

`GET /api/beta/menus`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include | ``null`` | Comma separated list of relationships to include in the response document. Must be ``null`` or one or several of the following: ``restaurant``, ``category``.
lat | ``null`` | Geospatial query's latitude. If defined, then ``lng`` and ``radius`` query parameters must also be defined.
lng | ``null`` | Geospatial query's longitude. If defined, then ``lat`` and ``radius`` query parameters must also be defined.
radius | ``null`` | Geospatial query's radius. If defined, then ``lat`` and ``lng`` query parameters must also be defined.
filter[categories] | ``null`` | Comma separated list of category IDs to filter. If ``null``, then all category types will be returned.

## Get a Specific Menu

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1"
```

> The above command returns JSON structured like this:

```json
{
	"data": {
		"type": "menus",
		"id": "1",
		"attributes": {
			"name": "Menu italien",
			"price": 11.95,
			"start": "2018-12-19T00:00:00+00:00",
			"end": "2018-12-20T00:00:00+00:00",
			"active": true
		},
		"relationships": {
			"restaurant": {
				"data": {
					"type": "restaurants",
					"id": "1"
				},
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1/restaurant"
				}
			},
			"categories": {
				"data": [{
					"type": "categories",
					"id": "1"
				}, {
					"type": "categories",
					"id": "2"
				}],
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1/categories"
				}
			},
			"dishes": {
				"data": [{
					"type": "dishes",
					"id": "1"
				}, {
					"type": "dishes",
					"id": "2"
				}],
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1/dishes"
				}
			}
		},
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1"
		}
	},
	"included": [{
		"type": "dishes",
		"id": "1",
		"attributes": {
			"name": "Lasagne",
			"dish-type": "main"
		}
	}, {
		"type": "dishes",
		"id": "2",
		"attributes": {
			"name": "Tiramisu",
			"dish-type": "dessert"
		}
	}]
}
```

This endpoint retrieves a specific menu.

Note that this endpoint will include its related dishes by default (no need to provide ``include=dishes`` query parameter).

### HTTP Request

`GET /api/beta/menus/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the menu to retrieve

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
include | ``null`` | Comma separated list of relationships to include in the response document. Must be ``null`` or one or several of the following: ``restaurant``, ``category``.

## Get a Specific Menu's Categories

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1/categories"
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

This endpoint retrieves the categories of a specific menu.

### HTTP Request

`GET /api/beta/menus/<ID>/categories`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the menu whose categories to retrieve

## Get a Specific Menu's Restaurant

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch//api/beta/menus/1/restaurant"
```

> The above command returns JSON structured like this:

```json
{
	"data": {
		"type": "restaurants",
		"id": "1",
		"attributes": {
			"name": "Foobar Restaurant",
			"active": true,
			"rate": 4.9,
			"location": {
				"lat": 47.1034892,
				"lng": 6.8327838
			},
			"address": "Fake Street 42",
			"zip": "2300",
			"city": "Foobar City",
			"avatar": "https://menufinder.srvz-webapp.he-arc.ch//storage/avatars/1.jpg",
			"website": "https://www.example.com",
			"description": "The best place where to eat!"
		},
		"relationships": {
			"menus": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants/1/menus"
				}
			}
		}
	},
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants/1"
	}
}
```

This endpoint retrieves the restaurant of a specific menu.

### HTTP Request

`GET /api/beta/menus/<ID>/restaurant`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the menu whose restaurant to retrieve

