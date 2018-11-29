# Menus

## Get All Menus

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus"
```

> The above command returns JSON structured like this:

```json
{
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1"
	},
	"data": [{
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
					"id": "18"
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
	}, {
		"type": "menus",
		"id": "2",
		"attributes": {
			"name": "Menu kebab",
			"price": 9.90,
			"start": "2018-11-05T00:00:00Z",
			"end": "2018-11-09T14:00:00Z",
			"active": true
		},
		"relationships": {
			"restaurant": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/2/restaurant"
				},
				"data": {
					"type": "restaurants",
					"id": "2"
				}
			},
			"category": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/2/category"
				},
				"data": {
					"type": "categories",
					"id": "3"
				}
			},
			"dishes": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/2/dishes"
				},
				"data": [{
					"type": "dishes",
					"id": "4"
				}]
			}
		}
	}]
}
```

This endpoint retrieves all menus or a list of menus queried by a geospatial query according to the restaurant's position and a given radius and/or a date.

### HTTP Request

`GET /api/beta/menus`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include | ``null`` | Comma separated list of relationships to include in the response document. Must be ``null`` or one or several of the following: ``restaurant``, ``category``, ``dishes``.
lat | ``null`` | Geospatial query's latitude. If defined, then ``lng`` and ``radius`` query parameters must also be defined.
lng | ``null`` | Geospatial query's longitude. If defined, then ``lat`` and ``radius`` query parameters must also be defined.
radius | ``null`` | Geospatial query's radius. If defined, then ``lat`` and ``lng`` query parameters must also be defined.
from | *timestamp of today at midnight* | Menu must be available within the range of time defined by ``from`` and ``to``. If defined, then ``to`` query parameter must also be defined.
to | *timestamp of tomorrow at midnight* | Menu must be available within the range of time defined by ``from`` and ``to``. If defined, then ``from`` query parameter must also be defined.

## Get a Specific Menu

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1"
```

> The above command returns JSON structured like this:

```json
{
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1"
	},
	"data": {
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
					"id": "18"
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
	},
	"included": [{
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants/1"
		},
		"type": "restaurants",
		"id": "1",
		"attributes": {
			"name": "Foobar Restaurant",
			"active": true,
			"rate": 4.9,
			"location": {
				"lat": 0.0,
				"lng": 0.0
			},
			"address": "Fake Street 42",
			"zip": "2300",
			"city": "Foobar City",
			"avatar": "https://menufinder.com/pictures/restaurants/1.jpg",
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
	}, {
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/categories/1"
		},
		"type": "categories",
		"id": "1",
		"attributes": {
			"name": "Chasse"
		}
	}, {
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/dishes/1"
		},
		"type": "dishes",
		"id": "1",
		"attributes": {
			"name": "Lasagne",
			"type": "main"
		}
	}, {
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/dishes/2"
		},
		"type": "dishes",
		"id": "2",
		"attributes": {
			"name": "Salade mêlée à la vinaigrette",
			"type": "starter"
		}
	}, {
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/dishes/3"
		},
		"type": "dishes",
		"id": "3",
		"attributes": {
			"name": "Tiramisu",
			"type": "dessert"
		}
	}]
}
```

This endpoint retrieves a specific menu.

### HTTP Request

`GET /api/beta/menus/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the menu to retrieve

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
include | ``null`` | Comma separated list of relationships to include in the response document. Must be ``null`` or one or several of the following: ``restaurant``, ``category``, ``dishes``.



## Get a Specific Menu Dishes

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1/dishes"
```

> The above command returns JSON structured like this:

```json
{
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/menus/1/dishes"
	},
	"data": [{
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
	}, {
		"type": "dishes",
		"id": "2",
		"attributes": {
			"name": "Salade mêlée à la vinaigrette",
			"type": "starter"
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
	}]
}
```

This endpoint retrieves a specific menu dishes (related resource link).

### HTTP Request

`GET /api/beta/menus/<ID>/dishes`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the menu whose dishes to retrieve


