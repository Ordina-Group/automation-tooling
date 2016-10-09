# Exercise: Implement a detail page and a router for navigation.

The goal of this exercise it to:
* Create a new component (contact-detail).
* Refactor the baseUrl for use in contact-card and contact-detail(image).

## Steps:

This part continues at the end of the components tags. To start:
```
$ git checkout step6-services-efficientSearch
```

### step1:
Refactor the baseUrl used in the contact-card, so it is provided in a global way.

### step2:
Create a new component contact-detail. This component should display all the contacts data.

### step3:
Create a router with 2 routes:
* / for the list-view
* /contact/{{id}} for the detail view.

Make the avatar in the list-view (on click) navigate to the detail component by using the RouterLink syntax.
