# Exercise: Implement a contacts service (with observables).

The goal of this exercise it to:
* Create a service.
* Refactor our app to use this service (remove contacts import).
* Refactor service to use http to call for the data.
* Refactor the app to use observables to get and  search for contacts
* Create unit tests for services and observables.

## Steps:

This part continues at the end of the components tags. To start:
`$ git checkout step2-components-contacts-list`

### step1:
Create a service and import the fixed data into this service. The use this service for serving contacts in all our components.
Don't forget to fix the others tests

### step2:
Refactor the service and use http to request the list of contacts.

The api is available at `ec2-52-49-175-247.eu-west-1.compute.amazonaws.com:4201/api`

it's a restfull service: (for now we only need a GET)
```
/jworks-contacts
```

Use
```
 {
     provide: 'API_ENDPOINT',
     useValue: 'http://ec2-52-49-175-247.eu-west-1.compute.amazonaws.com:4201/api'
 }
```
to expose this end point.


### step3:
Add search functionality to the list-component.
* Add a search input field in the list-component.
* Add a search function in the list-component and the service.

The service can call
```
/search?term=XXXXX
```
for search results.

As you can see, each input will trigger a search and stress the backend.
We will create a more efficient way in the next step.

### step3:
Add a debounce and unique check before making the call.
* Add a Subject
* Add a prefilter for debounce and uniqueness of the search term.
