# Static-Aviation-APIs
Aviation Edge [Static Aviation APIs](https://aviation-edge.com/premium-api/) **(please see the second table on the hyperlinked page)** provide static data on various, aviation-related subjects that are airports, nearby airports, registered airplanes, airplane models, airlines, cities, countries, and aviation taxes. Each group is provided through its own API with their own filters available.
A limit to the number of items returned can be set by using the "&limit=X" parameter with each API. This way, the API will return the first "X" items in the database as per the request.

### Documentation
You may find input parameters, output examples with explanations for each item, filter list, and more in the [documentation](https://aviation-edge.com/developers/).

## Nearby API

### Request 
Airports and cities nearby a certain latitude or longitude, within a certain distance in radius:

**GET** http://aviation-edge.com/v2/public/nearby?key=[API_KEY]&lat=-5.466667&lng=122.6333&distance=100

### Response
```
[
{
"code": "BUW",
"icao": "WAWB",
"name": "Baubau",
"cityCode": "BUW",
"cityName": "Baubau",
"countryCode": "ID",
"countryName": "Indonesia",
"lat": -5.466667,
"lng": 122.63333,
"timezone": "Asia/Makassar",
"type": "airport",
"isRailRoad": 0,
"isBusStation": 0, "distance": 0 },
{
"code": "RAQ",
"icao": "WAWR",
"name": "Sugimanuru",
"cityCode": "RAQ",
"cityName": "Raha",
"countryCode": "ID",
"countryName": "Indonesia",
"lat": -4.916667,
"lng": 122.583336,
"timezone": "Asia/Makassar",
"type": "airport",
"isRailRoad": 0,
"isBusStation": 0,
"distance": 61404
}
]
```

## Airlines API

### Request 
Entire database of airlines:

**GET** https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]

Data on a specific airline, you can search based on IATA airline code:

**GET** https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]&codeIataAirline=AA

Airlines based on the country code:

**GET** https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]&codeIso2Country=US

### Response
```
[ 
    { 
        "airlineId": "1", 
        "nameAirline": "American Airlines", 
        "codeIataAirline": "AA", 
        "iataPrefixAccounting": "1", 
        "codeIcaoAirline": "AAL", 
        "callsign": "AMERICAN", 
        "type": "scheduled", 
        "statusAirline": "active", 
        "sizeAirline": "963", 
        "ageFleet": "10.9", 
        "founding": "1934", 
        "codeHub": "DFW", 
        "nameCountry": "United States", 
        "codeIso2Country": "US" 
    }
]
```

## Airplanes API

### Request 
Entire database of airplanes:

**GET** https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]

Data on a specific airplane based on registration number. 

**GET** https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&numberRegistration=HB-JVE

Airplanes based on the hex ICAO code. 

**GET** https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&hexIcaoAirplane=4B19EA

Data on airplanes of a specific airline based on airline IATA code. 

**GET** https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&codeIataAirline=AA

### Response
```
[ 
    { 
      "airplaneId": "55", 
      "numberRegistration": "HB-JVE", 
      "productionLine": "Fokker 28/70/100", 
      "airplaneIataType": "F28 MK0100", 
      "planeModel": "F-100", 
      "modelCode": "F100", 
      "hexIcaoAirplane": "4B19EA", 
      "codeIataPlaneShort": "100", 
      "codeIataPlaneLong": "F100", 
      "constructionNumber": "11459", 
      "numberTestRgistration": "PH-EZD", 
      "rolloutDate": "0000-00-00", 
      "firstFlight": "1993-05-31T22:00:00.000Z", 
      "deliveryDate": "1993-06-29T22:00:00.000Z", 
      "registrationDate": "2004-05-11T22:00:00.000Z", 
      "lineNumber": "", 
      "planeSeries": "", 
      "codeIataAirline": "2L", 
      "codeIcaoAirline": "", 
      "planeOwner": "", 
      "enginesCount": "2", 
      "enginesType": "JET", 
      "planeAge": "24", 
      "planeStatus": "active", 
    } 
 ]
```

## Airplane-Types API

### Request 
Entire database of Aircraft types:

**GET** https://aviation-edge.com/v2/public/planeTypeDatabase?key=[API_KEY]

Data on a specific Aircraft type based on the IATA code:

**GET** https://aviation-edge.com/v2/public/planeTypeDatabase?key=[API_KEY]&codeIataAircraft=100

### Response
```
[
{
"planeTypeId": "100",
"nameAircraft": "Boeing 767-200 Freighter",
"codeIataAircraft": "76X"
},
{
"planeTypeId": "101",
"nameAircraft": "Boeing 767-300 Freighter",
"codeIataAircraft": "76Y"
},
{
"planeTypeId": "102",
"nameAircraft": "Boeing 777-200/200ER",
"codeIataAircraft": "772"
},
{ "planeTypeId": "103",
"nameAircraft": "Boeing 777-300",
"codeIataAircraft": "773"
},
{ "planeTypeId": "104",
"nameAircraft": "Boeing 777",
"codeIataAircraft": "777"
},
...
]
```

## Airports API

### Request 
Entire database of airports:

**GET** https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]

Data on a specific airport based on IATA code:

**GET** https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]&codeIataAirport=AAH

Airports in a country:

**GET** https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]&codeIso2Country=DE

### Response
```
[
    {
        "airportId": "7",
        "nameAirport": "Aachen/Merzbruck",
        "codeIataAirport": "AAH",
        "codeIcaoAirport": "EDKA",
        "latitudeAirport": "50.75",
        "longitudeAirport": "6.133333",
        "geonameId": "3247449",
        "timezone": "Europe/Berlin",
        "GMT": "1",
        "phone": "",
        "nameCountry": "Germany",
        "codeIso2Country": "DE",
        "codeIataCity": "AAH"
    }
]
```

## Cities API

### Request 
Entire database of cities. 

**GET** https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]

Data on a specific city based on IATA code. 

**GET** https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]&codeIataCity=MAN

Cities in a specific country:

**GET** https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]&codeIso2Country=GB

### Response
```
[
    {
          "GMT":"0",
          "cityId":4431,
          "codeIataCity":"MAN",
          "codeIso2Country":"GB",
          "geonameId":2643123,
          "latitudeCity":53.480713,
          "longitudeCity":-2.234377,
          "nameCity":"Manchester",
          "timezone":"Europe/London"
    }
]
```

## Countries API

### Request 
Entire database of countries:

**GET** https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]

Data on a specific country based on ISO code:

**GET** https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]&codeIso2Country=AD 

Data on a specific country based on name: 

**GET** https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]&nameCountry=Andorra

### Response
```
[
    {
        "countryId": "1",
        "nameCountry": "Andorra",
        "codeIso2Country": "AD",
        "codeIso3Country": "AND",
        "numericIso": "20",
        "population": "84000",
        "capital": "Andorra la Vella",
        "continent": "EU",
        "nameCurrency": "Euro",
        "codeCurrency": "EUR",
        "codeFips": "AN",
        "phonePrefix": "376"
    }
]
```

## Taxes API

### Request 
Entire database of taxes:

**GET** https://aviation-edge.com/v2/public/taxDatabase?key=[API_KEY]

Data on about a specific tax code, input the IATA tax code.

**GET** https://aviation-edge.com/v2/public/taxDatabase?key=[API_KEY]&codeIataTax=AC 

### Response
```
[
    {
        "taxId": "1",
        "nameTax": "Government Tax",
        "codeIataTax": "AB"
    }
]
```

### Access & Support
[Contact us](https://aviation-edge.com/contact/) via email for any questions or support requests.

[Get your API key](https://aviation-edge.com/premium-api/) in a minute and start testing the data right away. The API is provided through API subscriptions. All plans grant access to the Airport Schedules API and other APIs with a difference of the monthly API call limit. Choose the best plan for you and upgrade, downgrade or cancel your plan anytime without  commitments.

### License
The use of the API is subject to Aviation Edge [Terms and Conditions](https://aviation-edge.com/api-terms-of-service/).
