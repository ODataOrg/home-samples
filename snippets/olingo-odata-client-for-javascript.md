# Step 0: Download the library file
Download the Olingo OData Client for JavaScript from [olingo.apache.org](http://olingo.apache.org/doc/javascript/download.html). Then add the reference below
```html
<script src="odatajs-4.0.0-beta-01.min.js" type="text/javascript"></script>
```

# Step 1: Requesting resources
```js
var serviceRoot = "http://services.odata.org/V4/%28S%28tkkiczwk32qiiu5tw1dqvofq%29%29/TripPinServiceRW/";
var headers = { "Content-Type": "application/json", Accept: "application/json" };
var request = {
    requestUri: serviceRoot + "People",
    method: "GET",
    headers: headers,
    data: null
};

odatajs.oData.request(
    request, 
    function (data, response) {
        var people = data.value;

    }, 
    function (err) {
        alert("Fail: " + err.Message);
    }
);
```
# Step 2: Requesting an individual resource
```js
var serviceRoot = "http://services.odata.org/V4/%28S%28tkkiczwk32qiiu5tw1dqvofq%29%29/TripPinServiceRW/";
var headers = { "Content-Type": "application/json", Accept: "application/json" };
var request = {
    requestUri: serviceRoot + "People('russellwhyte')",
    method: "GET",
    headers: headers,
    data: null
};

odatajs.oData.request(
    request, 
    function (data, response) {
        var russell = data;

    }, 
    function (err) {
        alert("Fail: " + err.Message);
    }
);
```
# Step 3: Queries
```js
var serviceRoot = "http://services.odata.org/V4/%28S%28tkkiczwk32qiiu5tw1dqvofq%29%29/TripPinServiceRW/";
var headers = { "Content-Type": "application/json", Accept: "application/json" };
var request = {
    requestUri: serviceRoot + "People?$top=2&$filter=Trips/any(d:d/Budget gt 3000)",
    method: "GET",
    headers: headers,
    data: null
};

odatajs.oData.request(
    request, 
    function (data, response) {
        var filtedPeople = data.value;
        var FirstName = filtedPeople[0].FirstName;

    }, 
    function (err) {
        alert("Fail: " + err.Message);
    }
);
```
# Step 4: Creating a new resource
```js
var serviceRoot = "http://services.odata.org/V4/%28S%28tkkiczwk32qiiu5tw1dqvofq%29%29/TripPinServiceRW/";
var headers = { "Content-Type": "application/json", Accept: "application/json" };
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
var request = {
    requestUri: serviceRoot + "People",
    method: "POST",
    headers: headers,
    data: newPerson
};

odatajs.oData.request(
    request, 
    function (data, response) {
        var createeRes = response;

    }, 
    function (err) {
        alert("Fail: " + err.Message);
    }
);
```
# Step 5: Relating resources
```js
var serviceRoot = "http://services.odata.org/V4/%28S%28tkkiczwk32qiiu5tw1dqvofq%29%29/TripPinServiceRW/";
var headers = { "Content-Type": "application/json", Accept: "application/json" };
var relateBody = {
    "@odata.id":"http://services.odata.org/V4/%28S%28tkkiczwk32qiiu5tw1dqvofq%29%29/TripPinServiceRW/People('russellwhyte')/Trips(0)"
};
var request = {
    requestUri: serviceRoot + "People('lewisblack')/Trips/$ref",
    method: "POST",
    headers: headers,
    data: relateBody
};

odatajs.oData.request(
    request, 
    function (data, response) {
        var res = response;

    }, 
    function (err) {
        alert("Fail: " + err.Message);
    }
);
```
# Step 6: Invoking a function
```js
var serviceRoot = "http://services.odata.org/V4/%28S%28tkkiczwk32qiiu5tw1dqvofq%29%29/TripPinServiceRW/";
var headers = { "Content-Type": "application/json", Accept: "application/json" };
var request = {
    requestUri: serviceRoot + "People('russellwhyte')/Trips(0)/Microsoft.OData.SampleService.Models.TripPin.GetInvolvedPeople()",
    method: "GET",
    headers: headers,
    data: null
};

odatajs.oData.request(
    request, 
    function (data, response) {
        var involvedPeople = data.value;

    }, 
    function (err) {
        alert("Fail: " + err.Message);
    }
);
```
