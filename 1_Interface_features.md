# Interface features

Before Java 8, interfaces can have only public abstract methods and no implementations can be added to the interface. It was not possible to add new functionality to the existing interface without forcing all implementing classes to create an implementation of the new methods, nor it was possible to create interface methods with an implementation.

When we need to add any new functionality to interface,then all the implementaion classes will undergo changes.

Starting with Java 8, interfaces can have static and default methods that, despite being declared in an interface, have a defined behavior.


## Static methods

Consider the following method of the interface (let’s call this interface Vehicle)

```
static String producer() {
    return "N&F Vehicles";
}
```

The static producer() method is available only through and inside of an interface. It can’t be overridden by an implementing class.
To call it outside the interface the standard approach for static method call should be used

```
String producer = Vehicle.producer();
```

## Default methods

Default methods are declared using the new default keyword. These are accessible through the instance of the implementing class and can be overridden.

Let’s add a default method to our Vehicle interface, which will also make a call to the static method of this interface:

```
default String getOverview() {
    return "ATV made by " + producer();
}
```

Assume that this interface is implemented by the class VehicleImpl. For executing the default method an instance of this class should be created:

```
Vehicle vehicle = new VehicleImpl();
String overview = vehicle.getOverview();
```
