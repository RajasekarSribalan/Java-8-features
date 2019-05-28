## Reference to a Instance Method

The following syntax can be used to shortened to code ***containingClass::methodName***.

**Let us see an example**

```
 public static void main(String[] args)
    {

        List<Person> persons = new ArrayList<>();
        persons.add(new Person("Raj", "22", "Chennai", "Male"));
        persons.add(new Person("Sekar", "22", "Chennai", "Male"));
        persons.add(new Person("Nikki", "21", "Madurai", "Female"));

        Person person = new Person();
        boolean value = persons.stream().anyMatch(eachPerson -> person.isEligible(eachPerson));

        System.out.println(value);
    }
```

The above code makes a call to person instance method *isEligible*.This can be modified by using only the reference.

```
 boolean value = persons.stream().anyMatch(person::isEligible);
```

**Let us see an example using Lambda**

```
public class Test
{

    public static void main(String[] args)
    {
        Test test = new Test();
        Flyable flyable = test::flyLikeBird;
        flyable.fly();
    }

    public void flyLikeBird()
    {
        System.out.println("I am flying....");
    }

}

interface Flyable
{
    void fly();
}
```
