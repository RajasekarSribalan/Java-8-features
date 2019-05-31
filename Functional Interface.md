# Functional Interface

Functional interface is an interface which has **`single abstract method`**.This concept has been introduced as part of Java 8.

*Note*: Abastract method is nothing but unimpleneted method i.e., method only declared in the interface and the implementation class will implement the method.

Functional interface can still have default and static methods.This is because default and static method will have the implementation in the interface itself.Still the interface will have only one abstratc method which can be treated as Functional interface.

Below is the example of functional interface.

```
public interface Animal
{

    void run();

}
```

The above interface is a valid functional interface since it has only one abstract method.

Below is another example.

```
public interface Animal
{

    void run();

    static void walk()
    {
        System.out.println("I am walking...");
    }

    default void talk()
    {
        System.out.println("I am talking...");
    }
}
```

The above is also a valid functional interface because it still has only one abstract method.Default and static methods are not considered because it has implemented in the interface itself.

