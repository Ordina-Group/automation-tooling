# Exercise: Implement a detail page and a router for navigation.

The goal of this exercise it to:
* Create a new component (contact-editor).
* Make it possible to edit existing contacts and save them.

## Steps:

This part continues at the end of the components tags. To start:
```
$ git checkout step7-routes-fromListToDetailAndBack
```

### step1:
Create a new view:
```
$ ng generate component contact-editor
```

NOTE: If index.ts file is not create in the components' folder, create it.

```javascript
import { Component, OnInit, Inject } from '@angular/core';
import { Router, ActivatedRoute } from '@angular/router';
import { Contact } from '../models/cc-contact';
import { JworksContactsService } from '../jworks-contacts.service';

@Component({
  selector: 'app-contact-editor',
  templateUrl: './contact-editor.component.html',
  styleUrls: ['./contact-editor.component.scss']
})
export class ContactEditorComponent implements OnInit {

  contact: Contact = <Contact>{ address: {}};

  constructor(private contactsService: JworksContactsService, private router: Router,
    private route: ActivatedRoute) {}

  ngOnInit() {
    this.contactsService.getContact(this.route.snapshot.params['id'])
                        .subscribe(contact => this.contact = contact);
  }
}
```
Notice that we initialize the contact with `contact: Contact = <Contact>{ address: {}};`


Import the component in the NgModule
```javascript
...
import { ContactEditorComponent } from './contact-editor';
...
...
  declarations: [
    AppComponent,
    HeaderComponent,
    ContactCardComponent,
    ContactsListComponent,
    ContactDetailComponent,
    ContactEditorComponent
  ],
...
```

Add a new route in our app.routes.ts:
```javascript
...
import { ContactEditorComponent } from './contact-editor';

const routes: Routes = [
  ...
  {
    path: 'contact/:id/edit',
    component: ContactEditorComponent
  },
  ...
];
...
```

This should be enough for the wiring of the new component.

### step2:
Add the contact form in the html.

```html
<md-card md-theme="'default'" class="container">
  <md-card-title>
    <span class="md-headline">{{contact?.name || 'New' }}</span>
    <span class="md-subhead"></span>  
  </md-card-title>
  <md-card-content layout="row" layout-align="space-between">
    <div class="md-content-inline">
        <md-card>
          <div class="row">
            <md-input placeholder="Email" [(ngModel)]="contact.email"></md-input>  
          </div>
          <div class="row">
            <md-input placeholder="Phone" [(ngModel)]="contact.phone"></md-input>
          </div>
          <div class="row">
            <md-input placeholder="Birthday" [(ngModel)]="contact.birthday"></md-input>
          </div>
          <div class="row">
            <md-input placeholder="Website" [(ngModel)]="contact.website"></md-input>
          </div>
        </md-card>
        <md-card>
        <fieldset>
          <legend><md-icon class="md-10">location_city</md-icon> Address</legend>
          <div class="row">
            <md-input placeholder="Street" [(ngModel)]="contact.address.street"></md-input>
          </div>
          <div class="row">
            <md-input placeholder="Zip" [(ngModel)]="contact.address.zip"></md-input>
          </div>
          <div class="row">
            <md-input placeholder="City" [(ngModel)]="contact.address.city"></md-input>
          </div>
          <div class="row">
            <md-input placeholder="Country" [(ngModel)]="contact.address.country"></md-input>
          </div>
        </fieldset>
        </md-card>
    </div>

  </md-card-content>
  <md-card-actions layout="column">
      <button md-mini-fab class="md-primary js-cancel" [routerLink]="['/contact', contact.id]" title="back">
        <md-icon class="md-36">close</md-icon>
      </button>
      <button md-mini-fab class="md-primary js-save" [routerLink]="['/contact', contact.id]" title="back">
        <md-icon class="md-36">check</md-icon>
      </button>
   </md-card-actions>
</md-card>
```
Notice that we start by added the routerLink twice (cancel and save), because we don't have any functionality to intercept the actions.
We also use the ngModel to bind our contact model in our form.
Since we cannot use '?', we need to initialize the contact in our controller.

Add a bit of extra styling.
```scss
md-input {
    width: 100%;
}
md-card-actions {
    text-align: center;
}
```

### step3:
We will now bind the save/cancel event with our controller and implement the right functionality.

First implement a function in our `ContactsService` for updating a contact.
```javascript
...
updateContact(contact: Contact) {
  return this.http.put(`${this.apiEndpoint}/jworks-contacts/${contact.id}`, contact);
}
...
```

Add some functionality in our editor component:
```javascript
...
 cancel (contact: Contact) {
   this.toDetails(contact);
 }

 save (contact: Contact) {
   this.contactsService.updateContact(contact)
                      .subscribe(() => this.toDetails(contact));
 }

 private toDetails (contact: Contact) {
   this.router.navigate(['/contact', contact.id ]);
 }
...
```
