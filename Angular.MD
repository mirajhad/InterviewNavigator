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

# Observable and Observer

Pattern matching of message passing from publisher to subscriber

1. **Observable** is like a youtube channel of someone else. (( It uploads new videos(data) from time to time, **so it is a data source** for you))
2. Your youtube account is an **Observer**
3. Your youtube account **(Observer)** can only get notifications about whether someone else's youtube channel **(Observable)** has uploaded a new video **(has new data)** or made a livestream **(new event)** only if you have **subscribed** to that channel

**(Observer subscribes Observable to listen for new data/any event)**

where observable is a data source, subscribe is like a method/function , Observer is generally on your side

# @Input Binding

An Input Property is a settable property, annoted with an @Input() decorator.

```
class ChildComponent
{
	@Input("someInputName"): propertyName: dataType
}

<app-child [someInputName]="valueOfParent">
</app-child>

```

# @Output Binding

An Output Property is an observable property, annoted with an @Output() decorator

```
classComponent
{
	@Output("someOutputName") : eventName: EventEmitter = new EventEmitter();
}

<app-child (someOutputName)="methodName()">
</app-child>
```

# Rxjs Subject

Plain Observable unicast the values to observable

subject class multicast the values to all observer at-a-time.

Subject = Observable + Array of Observers

```
var mySubject = new Subject<dataType>();
subject.next(data);

mySubject.subscribe((data)=>{
//so something
})
```

# Rxjs BehaviourSubject

BehaviourSubject stores the current value which is lastly broadcast to the observer.

# ContentChild

child to grandChild

# ElementRef

Represent plain html tags of the template

```
<div #refvariable></div>

class Component
{
	@ViewChild("refvariable"): variableName:ElementRef
}
```
