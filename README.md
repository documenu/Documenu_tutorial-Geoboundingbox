![](https://res.cloudinary.com/deg2db9ip/image/upload/v1607243698/documenu-email-logo-blue_vgqfw9.png)

#[Documenu](https://documenu.com?utm_source=github&utm_medium=tutorial&utm_campaign=geoboundingbox)

## US Restaurant Menu API

***

### Tutorial | Get Restaurants In Geo Bounding Box

Documenu takes advantage of various types of geojson plotting to provide greater flexibility with your searches. This tutorial goes over using a geobounding box to search.

First use a tool that will provide you with the points that you need. My api takes two inputs, top left and bottom right of a bounding box. The tool i like to use is: https://geojson.io/ 

Then Use this Tool here:
![](https://res.cloudinary.com/deg2db9ip/image/upload/v1607611960/Documenu-Tutorials/Screen_Shot_2020-12-10_at_8.27.00_AM_ckcnyl.png)

To draw your desired bounding box like this:

![](https://res.cloudinary.com/deg2db9ip/image/upload/v1607611966/Documenu-Tutorials/Screen_Shot_2020-12-10_at_8.23.06_AM_i3bis6.png)

You will see the right side fill in with a GeoJson Feature. There will be an array of 5 points. 
> 1 and 5 will be the same
> **2 will be the `bottom_right` of the box**
> **4 will be the `top_left` of the box**

```json
[
  [
    -74.4488525390625,
    40.3549167507906
  ],
  [
    -73.3502197265625, //bottom_right
    40.3549167507906
  ],
  [
    -73.3502197265625,
    41.14143302653628
  ],
  [
    -74.4488525390625,  //top_left
    41.14143302653628
  ],
  [
    -74.4488525390625,
    40.3549167507906
  ]
]
```

My Api takes input for bothh `top_left` and `bottom_right` as lat,lon but these coordinate are lon,lat so you just need to flip them. 

For example I will take the `bottom_right` coordinates:

```json
  [
    -73.3502197265625, //bottom_right
    40.3549167507906
  ]
```

And flip them to use them as input into the API endpoint: `40.3549167507906,-73.3502197265625`

Do the same with the `top_left` coordinates and you have the inputs you will need.
```
bottom_right=40.3549167507906,-73.3502197265625
top_left=41.14143302653628,-74.4488525390625
```

Now just put them in as a query parameter in the API url, along with your api key:
[Get An API Key Here](https://documenu.com/register?utm_source=github&utm_medium=tutorial&utm_campaign=geoboundingbox)

`https://documenu.p.rapidapi.com/restaurants/geobbox?size=5&top_left=41.14143302653628,-74.4488525390625&bottom_right=40.3549167507906,-73.3502197265625&YOUR_API_KEY`


And the response from the API is this:


```json
{
  "totalResults": 53100,
  "page": 1,
  "total_pages": 10621,
  "more_pages": true,
  "data": [
    {
      "restaurant_name": "Dunkin",
      "restaurant_phone": "(631) 420-0387",
      "restaurant_website": "https://www.dunkindonuts.com?utm_source=yext&utm_medium=local&utm_campaign=localmaps&utm_content=354640",
      "hours": "",
      "price_range": "",
      "restaurant_id": 4073460073424000,
      "cuisines": [],
      "address": {
        "city": "Farmingdale",
        "state": "NY",
        "postal_code": "11735",
        "street": "1278 Broadhollow Rd",
        "formatted": "1278 Broadhollow Rd Farmingdale, NY 11735"
      },
      "geo": {
        "lat": 40.7346,
        "lon": -73.424
      },
      "menus": [],
      "last_updated": "2020-12-05T23:55:38.165Z"
    },
    {
      "restaurant_name": "Soup Man",
      "restaurant_phone": "(203) 622-0374",
      "restaurant_website": "http://www.originalsoupman.com",
      "hours": "",
      "price_range": "",
      "restaurant_id": 4102675273631590,
      "cuisines": [
        "American",
        "Salads",
        "Soups"
      ],
      "address": {
        "city": "GREENWICH",
        "state": "CT",
        "postal_code": "06830",
        "street": "160 W Putnam Ave",
        "formatted": "160 W Putnam Ave GREENWICH, CT 06830"
      },
      "geo": {
        "lat": 41.026752,
        "lon": -73.63159
      },
      "menus": [],
      "last_updated": "2020-12-05T23:31:03.714Z"
    },
    {
      "restaurant_name": "Starbucks Coffee",
      "restaurant_phone": "(203) 629-0432",
      "restaurant_website": "http://www.starbucks.com",
      "hours": "",
      "price_range": "",
      "restaurant_id": 4103664773602505,
      "cuisines": [
        "American",
        "Coffee & Tea"
      ],
      "address": {
        "city": "GREENWICH",
        "state": "CT",
        "postal_code": "06830",
        "street": "78 E Putnam Ave",
        "formatted": "78 E Putnam Ave GREENWICH, CT 06830"
      },
      "geo": {
        "lat": 41.036647,
        "lon": -73.602505
      },
      "menus": [],
      "last_updated": "2020-12-05T23:31:03.895Z"
    },
    {
      "restaurant_name": "Subway",
      "restaurant_phone": "(203) 622-1515",
      "restaurant_website": "http://www.subway.com",
      "hours": "",
      "price_range": "",
      "restaurant_id": 4103052773626938,
      "cuisines": [
        "Sandwiches"
      ],
      "address": {
        "city": "GREENWICH",
        "state": "CT",
        "postal_code": "06830",
        "street": "26 Greenwich Ave",
        "formatted": "26 Greenwich Ave GREENWICH, CT 06830"
      },
      "geo": {
        "lat": 41.030527,
        "lon": -73.626938
      },
      "menus": [],
      "last_updated": "2020-12-05T23:31:03.901Z"
    },
    {
      "restaurant_name": "Subway",
      "restaurant_phone": "(203) 869-3263",
      "restaurant_website": "http://www.subway.com",
      "hours": "",
      "price_range": "",
      "restaurant_id": 4102476273625561,
      "cuisines": [
        "Sandwiches"
      ],
      "address": {
        "city": "GREENWICH",
        "state": "CT",
        "postal_code": "06830",
        "street": "315 Greenwich Ave",
        "formatted": "315 Greenwich Ave GREENWICH, CT 06830"
      },
      "geo": {
        "lat": 41.024762,
        "lon": -73.625561
      },
      "menus": [],
      "last_updated": "2020-12-05T23:31:03.911Z"
    }
  ],
  "numResults": 5
}
```

Its that simple. If you want to try this yourself, all you need to go is sign up for a free account at [Documenu.com](https://documenu.com/register?utm_source=github&utm_medium=tutorial&utm_campaign=geoboundingbox)

Free Accounts can make up to 500 API calls a month. Or you can check out our other priing plans here: [Pricing](https://documenu.com/pricing?utm_source=github&utm_medium=tutorial&utm_campaign=geoboundingbox)

