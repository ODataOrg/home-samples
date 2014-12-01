# Step 1: Requesting resources
```csharp
var context = new DefaultContainer(new Uri("http://services.odata.org/v4/TripPinServiceRW/"));
var people = context.People.Execute();
```

# Step 2: Requesting an individual resource
```csharp
var context = new DefaultContainer(new Uri("http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/"));
var person = context.People.ByKey(userName: "russellwhyte").GetValue();
```

# Step 3: Queries
```csharp
var context = new DefaultContainer(new Uri("http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/"));
var people =
    context.People.Where(c => c.Trips.Any(d => d.Budget > 3000))
        .Take(2)
        .Select(c => new {c.FirstName, c.LastName});
```

# Step 4: Creating a new resource
```csharp
var context = new DefaultContainer(new Uri("http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/"));
var lewis = new Person()
{
    UserName = "lewisblack",
    FirstName = "Lewis",
    LastName = "Black",
    Emails = new ObservableCollection<string>() {"lewisblack@example.com"},
    AddressInfo =
        new ObservableCollection<Location>()
        {
            new Location()
            {
                Address = "187 Suffolk Ln.",
                City = new City() {CountryRegion = "United States", Name = "Boise", Region = "ID"}
            }
        },
    Gender = PersonGender.Male,
    Concurrency = 635519729375200400
};
context.AddObject("People", person);
context.SaveChanges();
```

# Step 5: Relating resources
```csharp
var context = new DefaultContainer(new Uri("http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/"));
 
var trip = context.People.ByKey(userName: "russellwhyte").Trips.ByKey(tripId: 0).GetValue();
var dsc = new DataServiceCollection<Person>(context)
{
    context.People.ByKey(userName: "lewisblack").GetValue()
};
dsc[0].Trips.Add(trip);
 
context.SaveChanges();
```

# Step 6: Invoking a function
```csharp
var context = new DefaultContainer(new Uri("http://services.odata.org/v4/(S(34wtn2c0hkuk5ekg0pjr513b))/TripPinServiceRW/"));
var trip = context.People.ByKey(userName: "russellwhyte").Trips.ByKey(tripId: 0).GetValue();
var people = trip.GetInvolvedPeople().Execute();
```
