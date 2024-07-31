# Reasoning Behind Open-Closed Principle

Consider an example in the code below. Different vehicles are serviced in a different manner. So, we have different classes for Bike and Car because the strategy to service a Bike is different from the strategy to service a Car. The Garage class accepts various kinds of vehicles for servicing.

Problem of Rigidity

Observe the code and see how the Garage class shows the signs of rigidity when it comes to introducing a new functionality:

```
class Bike {
    public void service() {
        System.out.println("Bike servicing strategy performed.");
    }
}

class Car {
    public void service() {
        System.out.println("Car servicing strategy performed.");
    }
}

class Garage {
    public void serviceBike(Bike bike) {
        bike.service();
    }

    public void serviceCar(Car car) {
        car.service();
    }
}
```

As you may have noticed, whenever some new vehicle like Truck or Bus is to be serviced, the Garage will need to be modified to define some new methods like serviceTruck() and serviceBus(). That means the Garage class must know every possible vehicle like Bike, Car, Bus, Truck and so on. So, it violates the open-closed principle by being open for modification. Also it's not open for extension because to extend the new functionality, we need to modify the class.


## Meaning Behind Open-Closed Principle

**Abstraction**

To solve the problem of rigidity in the code above we can use the open-closed principle. That means we need to make the `Garage` class dumb by taking away the implementation details of servicing of every vehicle that it knows. In other words we should abstract the implementation details of the servicing strategy for each concrete type like `Bike` and `Car`.

To abstract the implementation details of the servicing strategies for various types of vehicles we use an `interface` called `Vehicle` and have an abstract method `service()` in it.

**Polymorphism**

At the same time, we also want the `Garage` class to accept *many forms* of the vehicle, like `Bus`, `Truck` and so on, not just `Bike` and `Car`. To do that, the open-closed principle uses *polymorphism* (many forms).

For the `Garage` class to accept many forms of the `Vehicle`, we change the signature of its method to `service(Vehicle vehicle) { }` to accept the interface `Vehicle` instead of the actual implementation like `Bike`, `Car` etc. We also remove the multiple methods from the class as just one method will accept many forms.

```
interface Vehicle {
    void service();
}

class Bike implements Vehicle {
    @Override
    public void service() {
        System.out.println("Bike servicing strategy performed.");
    }
}

class Car implements Vehicle {
    @Override
    public void service() {
        System.out.println("Car servicing strategy performed.");
    }
}

class Garage {
    public void service(Vehicle vehicle) {
        vehicle.service();
    }
}
```


## Importance of Open-Closed Principle

**Closed for modification**

As you can see in the code above, now the `Garage` class has become closed for modification because now it doesn't know about the implementation details of servicing strategies for various types of vehicles and can accept any type of new `Vehicle`. We just have to extend the new vehicle from the `Vehicle` interface and send it to the `Garage`. That's it! We don't need to change any code in the `Garage` class.

Another entity that's closed for modification is our `Vehicle` interface. We don't have to change the interface to extend the functionality of our software.

**Open for extension**

The `Garage` class now becomes open for extension in the context that it will support the new types of `Vehicle`, without the need for modifying.

Our `Vehicle` interface is open for extension because to introduce any new vehicle, we can extend from the `Vehicle` interface and provide a new implementation with a strategy for servicing that particular vehicle.

**Strategy Design Pattern**

Did you notice that I used the word *strategy* multiple times? That's because this is also an example of the Strategy Design Pattern. We can implement different strategies for servicing different types of `Vehicle`s by extending it. For example, servicing a `Truck` has a different strategy from the strategy of servicing a `Bus`. So we implement these strategies inside the different derived classes.

The strategy pattern allows our software to be flexible as the requirements change over time. Whenever the client changes their strategy, just derive a new class for it and provide it to the existing component, no need to change other stuff! The open-closed principle plays an important role in implementing this pattern.
