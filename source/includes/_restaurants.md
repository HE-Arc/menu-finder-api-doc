# Restaurants

## Get All Restaurants

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants"
```

> The above command returns JSON structured like this:

```json
{
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants"
	},
	"data": [{
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
		"type": "restaurants",
		"id": "2",
		"attributes": {
			"name": "Barfoo Restaurant",
			"active": true,
			"rate": 1.1,
			"location": {
				"lat": 46.992979,
				"lng": 6.931933
			},
			"address": "Fake Street 24",
			"zip": "2000",
			"city": "Barfoo City",
			"avatar": "https://menufinder.com/pictures/restaurants/2.jpg",
			"website": "https://www.example.net",
			"description": "The worst place where to eat!"
		},
		"relationships": {
			"menus": {
				"links": {
					"related": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants/2/menus"
				}
			}
		}
	}]
}
```

This endpoint retrieves all restaurants or a list of restaurants within a certain radius of a given position.

### HTTP Request

`GET /api/beta/restaurants`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
lat | ``null`` | Geospatial query's latitude. If defined, then ``lng`` and ``radius`` query parameters must also be defined.
lng | ``null`` | Geospatial query's longitude. If defined, then ``lat`` and ``radius`` query parameters must also be defined.
radius | ``null`` | Geospatial query's radius. If defined, then ``lat`` and ``lng`` query parameters must also be defined.

## Get a Specific Restaurant

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants/1"
```

> The above command returns JSON structured like this:

```json
{
	"links": {
		"self": "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants/1"
	},
	"data": {
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
	}
}
```

This endpoint retrieves a specific restaurant.

### HTTP Request

`GET /api/beta/restaurants/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the restaurant to retrieve
