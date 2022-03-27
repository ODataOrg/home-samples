# Step 0: Install Python 3 and requests module
Download and install the Python 3 then install with pip command 'requests' library. You can now run the snippet with python command. 

# Step 1: Requesting resources
```Python
import requests

baseUrl = "http://services.odata.org/v4/TripPinServiceRW/"
response = requests.get(baseUrl +"People")

if response.status_code != 200:
    print("error: " + str(response.status_code))
    print(response.text)
else:
    print("success")
    print(response.json())

```

# Step 2: Requesting an individual resource
```Python
import requests

baseUrl = "http://services.odata.org/v4/TripPinServiceRW/"
response = requests.get(baseUrl +"People('russellwhyte')")

if response.status_code != 200:
    print("error: " + str(response.status_code))
    print(response.text)
else:
    print("success")
    print(response.json())
```

# Step 3: Queries
```Python
import requests

baseUrl = "http://services.odata.org/v4/TripPinServiceRW/"

queryparams = {
    "$top":2,
    "$select":"FirstName, LastName",
    "$filter":"Trips/any(d:d/Budget gt 3000)"
}

response = requests.get(baseUrl +"People", params=queryparams)

if response.status_code != 200:
    print("error: " + str(response.status_code))
    print(response.text)
else:
    print("success")
    print(response.json())
```

# Step 4: Creating a new resource
```Python
```

# Step 5: Relating resources
```Python
```