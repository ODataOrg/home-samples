# Step 0: Install Node.js
Download and install the Node.js platform from [nodejs.org] then run the snippets below using the node command.

# Step 1: Requesting resources
```js
var http = require("http");
var serviceRoot = "http://services.odata.org/v4/TripPinServiceRW/";

getURL(serviceRoot + "/People");

function getURL(url) {
    var body = "";
    http.get(url, function (response) {
        response.on('data', function (chunk) {
            body+=chunk;
        });
        response.on('end', function () {
            console.log(body);
        });

    }).on('error', function(e) {
        console.log("ERROR: " + e.message);
    });
}
```
# Step 2: Requesting an individual resource
```js
var http = require("http");
var serviceRoot = "http://services.odata.org/v4/TripPinServiceRW/";

getURL(serviceRoot + "People('russellwhyte')");

function getURL(url) {
    var body = "";
    http.get(url, function (response) {
        response.on('data', function (chunk) {
            body+=chunk;
        });
        response.on('end', function () {
            console.log(body);
        });

    }).on('error', function(e) {
        console.log("ERROR: " + e.message);
    });
}
```
# Step 3: Queries
```js
var http = require("http");
var serviceRoot = "http://services.odata.org/v4/TripPinServiceRW/";

getURL(serviceRoot + "People?$top=2 & $select=FirstName, LastName & $filter=Trips/any(d:d/Budget gt 3000)");

function getURL(url) {
    var body = "";
    http.get(url, function (response) {
        response.on('data', function (chunk) {
            body+=chunk;
        });
        response.on('end', function () {
            console.log(body);
        });

    }).on('error', function(e) {
        console.log("ERROR: " + e.message);
    });
}
```
# Step 4: Creating a new resource
```js
var http = require("http");
var serviceHost = "services.odata.org";
var servicePath = "/v4/TripPinServiceRW/";

var newPerson = {
    UserName:"lewisblack",
    FirstName:"Lewis",
    LastName:"Black",
    Emails:[
        "lewisblack@example.com"
    ],
    AddressInfo:[
        {
            Address: "187 Suffolk Ln.",
            City: {
                CountryRegion: "United States",
                Name: "Boise",
                Region: "ID"
            }
        }
    ],
    Gender: "Male"
};

var postData = JSON.stringify(newPerson);

var options = {
    hostname: serviceHost,
    path: servicePath + "People",
    port: 80,
    method: 'POST',
    headers: {
        'OData-Version': '4.0',
        'OData-MaxVersion': '4.0',
        'Content-Type': 'application/json',
        'Content-Length': postData.length
    }
};

var req = http.request(options, function(res) {
    var body = "";
    res.on('data', function (chunk) {
        body += chunk;
    });
    res.on('end', function () {
        console.log(body);
    });
});

req.on('error', function(e) {
    console.log('ERROR: ' + e.message);
});

req.write(postData);
req.end();
```
# Step 5: Relating resources
```js
var http = require("http");
var serviceHost = "services.odata.org";
var servicePath = "/v4/TripPinServiceRW/";

var postData = JSON.stringify({
    "@odata.id": "http://services.odata.org/V4/TripPinServiceRW/People('russellwhyte')/Trips(0)"
});

var options = {
    hostname: serviceHost,
    path: servicePath + "People('lewisblack')/Trips/$ref",
    port: 80,
    method: 'POST',
    headers: {
        'OData-Version': '4.0',
        'OData-MaxVersion': '4.0',
        'Content-Type': 'application/json',
        'Content-Length': postData.length
    }
};

var req = http.request(options, function(res) {
    var body = "";
    res.on('data', function (chunk) {
        body += chunk;
    });
    res.on('end', function () {
        console.log(body);
    });
});

req.on('error', function(e) {
    console.log('problem with request: ' + e.message);
});

req.write(postData);
req.end();
```
# Step 6: Invoking a function
```js
var http = require("http");
var serviceRoot = "http://services.odata.org/v4/TripPinServiceRW/";

getURL(serviceRoot + "People('russellwhyte')/Trips(0)/Microsoft.OData.SampleService.Models.TripPin.GetInvolvedPeople()");

function getURL(url) {
    var body = "";
    http.get(url, function (response) {
        response.on('data', function (chunk) {
            body+=chunk;
        });
        response.on('end', function () {
            console.log(body);
        });

    }).on('error', function(e) {
        console.log("ERROR: " + e.message);
    });
}
```
