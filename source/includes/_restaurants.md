# Restaurants

## Get All Restaurants

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants"
```

> The above command returns JSON structured like this:

```json
{
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
			"avatar": "https://menufinder.srvz-webapp.he-arc.ch//storage/avatars/1.jpg",
			"website": "https://www.example.com",
			"description": "The best place where to eat!"
		},
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/restaurants/1"
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
			"avatar": "https://menufinder.srvz-webapp.he-arc.ch//storage/avatars/2.jpg",
			"website": "https://www.example.net",
			"description": "The worst place where to eat!"
		},
		"links": {
			"self": "https://menufinder.srvz-webapp.he-arc.ch//api/beta/restaurants/2"
		}
	}]
}
```

This endpoint retrieves all restaurants.

### HTTP Request

`GET /api/beta/restaurants`

## Get a Specific Restaurant

```shell
curl "https://menufinder.srvz-webapp.he-arc.ch/api/beta/restaurants/1"
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

This endpoint retrieves a specific restaurant.

### HTTP Request

`GET /api/beta/restaurants/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the restaurant to retrieve
