# **Life Cycle**

* ngOnChanges: When the value of a data bound property changes, then this method is called.
* ngOnInit: This is called whenever the initialization of the directive/component after Angular first displays the data-bound properties happens.
* ngDoCheck: This is for the detection and to act on changes that Angular can't or won't detect on its own.
* ngAfterContentInit: This is called in response after Angular projects external content into the component's view
* ngAfterContentChecked: This is called in response after Angular checks the content projected into the component.
* ngAfterViewInit: This is called in response after Angular initializes the component's views and child views.
* ngAfterViewChecked: This is called in response after Angular checks the component's views and child views.
* ngOnDestroy: This is the cleanup phase just before Angular destroys the directive/component.

# **Two-way data binding:**

[(ngModel)]=”value”: Two-way data binding allows to have the data flow both ways. For example, in the below code snippet, both the email DOM input and component email property are in sync

```
 <input type="email" [(ngModel)]="user.email">    
```

# Async Pipe


# **BehaviorSubject**

A Subject or Observable doesn't have a current value. When a value is emitted, it is passed to subscribers and the Observable is done with it.

If you want to have a current value, use BehaviorSubject which is designed for exactly that purpose. BehaviorSubject keeps the last emitted value and emits it immediately to new subscribers.

It also has a method getValue() to get the current value.
