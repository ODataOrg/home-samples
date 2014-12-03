# Step 1: Requesting resources
```C++
auto service_context = std::make_shared<DefaultContainer>(U("http://services.odata.org/V4/(S(khax213ynjvk4pqdhdgcadvw))/TripPinServiceRW/"));
auto people = service_context->create_people_query()->execute_query().get();
```

# Step 2: Requesting an individual resource
```C++  
auto service_context = std::make_shared<DefaultContainer>(U("http://services.odata.org/V4/(S(khax213ynjvk4pqdhdgcadvw))/TripPinServiceRW/"));
auto people = service_context->create_people_query()->key(U("'russellwhyte'"))->execute_query().get();
```

# Step 3: Queries
```C++
auto service_context = std::make_shared<DefaultContainer>(U("http://services.odata.org/V4/(S(khax213ynjvk4pqdhdgcadvw))/TripPinServiceRW/"));
auto people = service_context->create_people_query()->filter(U("Trips/any(d:d/Budget gt 3000)"))->select(U("FirstName, LastName"))->top(2)->execute_query().get();
```

# Step 4: Creating a new resource
```C++
auto service_context = std::make_shared<DefaultContainer>(U("http://services.odata.org/V4/(S(khax213ynjvk4pqdhdgcadvw))/TripPinServiceRW/"));
auto lewis = std::make_shared<Person>(service_context);
lewis->set_username(U("lewisblack"));
lewis->set_firstname(U("Lewis"));
lewis->set_lastname(U("Black"));
lewis->set_emails({ U("lewisblack@example.com") });
auto location = std::make_shared<Location>(service_context);
location->set_address(U("187 Suffolk Ln."));
auto city = std::make_shared<City>(service_context);
city->set_countryregion(U("United States"));
city->set_name(U("Boise"));
city->set_region(U("ID"));
location->set_city(city);
lewis->set_addressinfo({ location });
lewis->set_gender(PersonGender::Male);
lewis->set_concurrency(635519729375200400);
service_context->add_object(U("People"), lewis).get();
```

# Step 5: Relating resources
```C++
auto service_context = std::make_shared<DefaultContainer>(U("http://services.odata.org/V4/(S(khax213ynjvk4pqdhdgcadvw))/TripPinServiceRW/"));
auto ronald = service_context->create_people_query()->key(U("'ronaldmundy'"))->execute_query().get()[0];
auto russell = service_context->create_people_query()->key(U("'russellwhyte'"))->expand(U("Trips"))->execute_query().get()[0];
auto trip = russell->get_trips()[0];
service_context->add_reference(ronald, U("Trips"), trip).get();
```

# Step 6: Invoking a function
```C++
auto service_context = std::make_shared<DefaultContainer>(U("http://services.odata.org/V4/(S(khax213ynjvk4pqdhdgcadvw))/TripPinServiceRW/"));
auto russell = service_context->create_people_query()->key(U("'russellwhyte'"))->expand(U("Trips"))->execute_query().get()[0];
auto trip = russell->get_trips()[0];
auto people = trip->GetInvolvedPeople().get();
```
