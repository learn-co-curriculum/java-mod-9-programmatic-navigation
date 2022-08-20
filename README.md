# Programmatic Navigation

## Learning Goals

- Perform actions before navigating to a link.

## Introduction

Sometimes, it may be the case that we want to navigate to a different route when
a user clicks on a button, but not before actually taking some action in our
controller, so we need a way for a button to be associated with a function in
our controller, allow us to execute some logic and then allow us to navigate to
a specific route.

## Implementation

Let's re-implement our "New Message" button this way:

- First we need to create a function in our
  `conversation-control-component.component.ts` file to be called when the "New
  Message" button is called:

```typescript
  onNewMessage() {
  }
```

- Then we need to import the `Router` module from Angular:

```typescript
import { Router } from "@angular/router";
```

- Then we need to ask Angular to inject a router instance into our component:

```typescript
  constructor(private router: Router) { }
```

- Finally, we can use the router instance to route the application to the right
  component in the `onNewMessage()` function:

```typescript
  onNewMessage() {
    this.router.navigate(['contactList']);
  }
```

Now that the controller code is ready, we can go into the view in
`conversation-control-component.component.html` and replace the `routerLink`
directive with an `onClick()` directive:

```html
<div class="float-end">
  <button class="btn btn-primary" (click)="onNewMessage()">
    <!-- Replace the [routerLink] directive with a (click) directive -->
    New Message
  </button>
</div>
```
