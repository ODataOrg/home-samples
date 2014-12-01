# Step 1: Requesting resources
Request:
```HTTP
GET http://services.odata.org/v4/TripPinServiceRW/People HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
```
Response:
```HTTP
HTTP/1.1 200 OK
 
Content-Length: 1007
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0
 
{
    "@odata.context": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/$metadata#People",
    "@odata.nextLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People?%24skiptoken=8",
    "value": [
        {
            "@odata.id": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('russellwhyte')",
            "@odata.etag": "W/"08D1D5BD423E5158"",
            "@odata.editLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('russellwhyte')",
            "UserName": "russellwhyte",
            "FirstName": "Russell",
            "LastName": "Whyte",
            "Emails": [
                "Russell@example.com",
                "Russell@contoso.com",
                null
            ],
            "AddressInfo": [
                {
                    "Address": "187 Suffolk Ln.",
                    "City": {
                        "CountryRegion": "United States",
                        "Name": "Boise",
                        "Region": "ID"
                    }
                },
                null
            ],
            "Gender": "Male",
            "Concurrency": 635524031272866200
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('scottketchum')",
            "@odata.etag": "W/"08D1D5BD423E5158"",
            "@odata.editLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('scottketchum')",
            "UserName": "scottketchum",
            "FirstName": "Scott",
            "LastName": "Ketchum",
            "Emails": [
                "Scott@example.com"
            ],
            "AddressInfo": [
                {
                    "Address": "2817 Milton Dr.",
                    "City": {
                        "CountryRegion": "United States",
                        "Name": "Albuquerque",
                        "Region": "NM"
                    }
                }
            ],
            "Gender": "Male",
            "Concurrency": 635524031272866200
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('ronaldmundy')",
            "@odata.etag": "W/"08D1D5BD423E5158"",
            "@odata.editLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('ronaldmundy')",
            "UserName": "ronaldmundy",
            "FirstName": "Ronald",
            "LastName": "Mundy",
            "Emails": [
                "Ronald@example.com",
                "Ronald@contoso.com"
            ],
            "AddressInfo": [ ],
            "Gender": "Male",
            "Concurrency": 635524031272866200
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('javieralfred')",
            "@odata.etag": "W/"08D1D5BD423E5158"",
            "@odata.editLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('javieralfred')",
            "UserName": "javieralfred",
            "FirstName": "Javier",
            "LastName": "Alfred",
            "Emails": [
                "Javier@example.com",
                "Javier@contoso.com"
            ],
            "AddressInfo": [
                {
                    "Address": "89 Jefferson Way Suite 2",
                    "City": {
                        "CountryRegion": "United States",
                        "Name": "Portland",
                        "Region": "WA"
                    }
                }
            ],
            "Gender": "Male",
            "Concurrency": 635524031272866200
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('willieashmore')",
            "@odata.etag": "W/"08D1D5BD423E5158"",
            "@odata.editLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('willieashmore')",
            "UserName": "willieashmore",
            "FirstName": "Willie",
            "LastName": "Ashmore",
            "Emails": [
                "Willie@example.com",
                "Willie@contoso.com"
            ],
            "AddressInfo": [ ],
            "Gender": "Male",
            "Concurrency": 635524031272866200
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('vincentcalabrese')",
            "@odata.etag": "W/"08D1D5BD423E5158"",
            "@odata.editLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('vincentcalabrese')",
            "UserName": "vincentcalabrese",
            "FirstName": "Vincent",
            "LastName": "Calabrese",
            "Emails": [
                "Vincent@example.com",
                "Vincent@contoso.com"
            ],
            "AddressInfo": [
                {
                    "Address": "55 Grizzly Peak Rd.",
                    "City": {
                        "CountryRegion": "United States",
                        "Name": "Butte",
                        "Region": "MT"
                    }
                }
            ],
            "Gender": "Male",
            "Concurrency": 635524031272866200
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('clydeguess')",
            "@odata.etag": "W/"08D1D5BD423E5158"",
            "@odata.editLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('clydeguess')",
            "UserName": "clydeguess",
            "FirstName": "Clyde",
            "LastName": "Guess",
            "Emails": [
                "Clyde@example.com"
            ],
            "AddressInfo": [ ],
            "Gender": "Male",
            "Concurrency": 635524031272866200
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('keithpinckney')",
            "@odata.etag": "W/"08D1D5BD423E5158"",
            "@odata.editLink": "http://services.odata.org/V4/(S(a2k31bgwiyejn2j2iiybvq4p))/TripPinServiceRW/People('keithpinckney')",
            "UserName": "keithpinckney",
            "FirstName": "Keith",
            "LastName": "Pinckney",
            "Emails": [
                "Keith@example.com",
                "Keith@contoso.com"
            ],
            "AddressInfo": [ ],
            "Gender": "Male",
            "Concurrency": 635524031272866200
        }
    ]
}
```

# Step 2: Requesting an individual resource
Request:
```HTTP
GET http://services.odata.org/v4/TripPinServiceRW/People('russellwhyte') HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
```
Response:
```HTTP
HTTP/1.1 200 OK
 
Content-Length: 482
Content-Type: application/json; odata.metadata=minimal
ETag: W/"08D1D5BE987DE78B"
OData-Version: 4.0
 
{
    "@odata.context": "http://services.odata.org/V4/(S(ak3ckilwx5ajembdktfunu0v))/TripPinServiceRW/$metadata#People/$entity",
    "@odata.id": "http://services.odata.org/V4/(S(ak3ckilwx5ajembdktfunu0v))/TripPinServiceRW/People('russellwhyte')",
    "@odata.etag": "W/"08D1D5BE987DE78B"",
    "@odata.editLink": "http://services.odata.org/V4/(S(ak3ckilwx5ajembdktfunu0v))/TripPinServiceRW/People('russellwhyte')",
    "UserName": "russellwhyte",
    "FirstName": "Russell",
    "LastName": "Whyte",
    "Emails": [
        "Russell@example.com",
        "Russell@contoso.com",
        null
    ],
    "AddressInfo": [
        {
            "Address": "187 Suffolk Ln.",
            "City": {
                "CountryRegion": "United States",
                "Name": "Boise",
                "Region": "ID"
            }
        },
        null
    ],
    "Gender": "Male",
    "Concurrency": 635524037014841200
}
```

# Step 3: Queries
Request:
```HTTP
var context = new DefaultContainer(new Uri("http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/"));
var people =
    context.People.Where(c => c.Trips.Any(d => d.Budget > 3000))
        .Take(2)
        .Select(c => new {c.FirstName, c.LastName});
```
Response:
```HTTP
HTTP/1.1 200 OK
 
Content-Length: 367
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0
 
{
    "@odata.context": "http://services.odata.org/V4/(S(cn0zbczilimhpqbgnre0usaz))/TripPinServiceRW/$metadata#People(FirstName,LastName)",
    "value": [
        {
            "@odata.id": "http://services.odata.org/V4/(S(cn0zbczilimhpqbgnre0usaz))/TripPinServiceRW/People('scottketchum')",
            "@odata.etag": "W/"08D1D5BEF93F01A6"",
            "@odata.editLink": "http://services.odata.org/V4/(S(cn0zbczilimhpqbgnre0usaz))/TripPinServiceRW/People('scottketchum')",
            "FirstName": "Scott",
            "LastName": "Ketchum"
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(cn0zbczilimhpqbgnre0usaz))/TripPinServiceRW/People('ronaldmundy')",
            "@odata.etag": "W/"08D1D5BEF93F01A6"",
            "@odata.editLink": "http://services.odata.org/V4/(S(cn0zbczilimhpqbgnre0usaz))/TripPinServiceRW/People('ronaldmundy')",
            "FirstName": "Ronald",
            "LastName": "Mundy"
        }
    ]
}
```

# Step 4: Creating a new resource
Request:
```HTTP
POST http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Length: 428
Content-Type: application/json
 
{
    "UserName":"lewisblack",
    "FirstName":"Lewis",
    "LastName":"Black",
    "Emails":[
        "lewisblack@example.com"
    ],
    "AddressInfo":[
        {
            Address: "187 Suffolk Ln.",
            City: {
                CountryRegion: "United States",
                Name: "Boise",
                Region: "ID"
            }
        }
    ],
    "Gender": "Male",
    "Concurrency":635519729375200400
}
```
Response:
```HTTP
HTTP/1.1 201 Created
 
Content-Length: 652
Content-Type: application/json;odata.metadata=minimal;odata.streaming=true;IEEE754Compatible=false;charset=utf-8
ETag: W/"08D1D3800FC572E3"
Location: http://services.odata.org/V4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People('lewisblack')
OData-Version: 4.0
```

# Step 5: Relating resources
Request:
```HTTP
POST http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People('lewisblack')/Trips/$ref HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Length: 123
Content-Type: application/json
 
{
    "@odata.id":"http://services.odata.org/V4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People('russellwhyte')/Trips(0)"
}
```
Response:
```HTTP
HTTP/1.1 204 No Content

OData-Version: 4.0
```

# Step 6: Invoking a function
Request:
```HTTP
GET http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People('russellwhyte')/Trips(0)/Microsoft.OData.SampleService.Models.TripPin.GetInvolvedPeople() HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
```
Response:
```HTTP
HTTP/1.1 200 OK
 
Content-Length: 582
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0
 
{
    "@odata.context": "http://services.odata.org/V4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/$metadata#People",
    "value": [
        {
            "@odata.id": "http://services.odata.org/V4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People('russellwhyte')",
            "@odata.etag": "W/"08D1D5BFB48CE017"",
            "@odata.editLink": "http://services.odata.org/V4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People('russellwhyte')",
            "UserName": "russellwhyte",
            "FirstName": "Russell",
            "LastName": "Whyte",
            "Emails": [
                "Russell@example.com",
                "Russell@contoso.com",
                null
            ],
            "AddressInfo": [
                {
                    "Address": "187 Suffolk Ln.",
                    "City": {
                        "CountryRegion": "United States",
                        "Name": "Boise",
                        "Region": "ID"
                    }
                },
                null
            ],
            "Gender": "Male",
            "Concurrency": 635524041780551700
        },
        {
            "@odata.id": "http://services.odata.org/V4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People('scottketchum')",
            "@odata.etag": "W/"08D1D5BFB48CE017"",
            "@odata.editLink": "http://services.odata.org/V4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/People('scottketchum')",
            "UserName": "scottketchum",
            "FirstName": "Scott",
            "LastName": "Ketchum",
            "Emails": [
                "Scott@example.com"
            ],
            "AddressInfo": [
                {
                    "Address": "2817 Milton Dr.",
                    "City": {
                        "CountryRegion": "United States",
                        "Name": "Albuquerque",
                        "Region": "NM"
                    }
                }
            ],
            "Gender": "Male",
            "Concurrency": 635524041780551700
        }
    ]
}
```
