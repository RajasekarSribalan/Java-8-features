## Reference to a Static Method

The following syntax can be used to shortened to code **ContainingClass::staticMethodName**.

*Let us see an example*

```
 public static void main(String[] args)
    {

        List<Person> persons = new ArrayList<>();
        persons.add(new Person("Raj", "22", "Chennai", "Male"));
        persons.add(new Person("Sekar", "22", "Chennai", "Male"));
        persons.add(new Person("Nikki", "21", "Madurai", "Female"));

        boolean value = persons.stream().anyMatch(p -> Person.isMale(p));
        
    }
```

The above code makes a call to static method of Person class.To simplify the code we can use below method reference.

```
 boolean value = persons.stream().anyMatch(Person::isMale);
```

This looks more elegant and readable.

*Let us see an example using Lambda*

Usually we will declare the lambda expression he functional interface as below.

```
public class Test
{

    public static void main(String[] args)
    {

        Flyable flyable = () -> System.out.println("I am flying");
        flyable.fly();
    }
}

interface Flyable
{
    void fly();
}

```

Consider we would like to refer to method in our lamdba expression.In this case we refer the method as below.

```
public class Test
{

    public static void main(String[] args)
    {

        Flyable flyable = Test::flyLikeBird;
        flyable.fly();
    }

    public static void flyLikeBird()
    {
        System.out.println("I am flying....");
    }

}

interface Flyable
{
    void fly();
}

```