# Reference to a constructor

The following syntax can be used to refer to a contructor ***Class::new***.

**Let us see an example**

```
public class Test
{
    public Test() {
        System.out.println("I am in contructor");
    }
    
    public Test(String arg) {
        System.out.println("I am in contructor with args "+arg);
    }

    public static void main(String[] args)
    {
        Flyable flyable = Test::new;
        flyable.fly();
        Talkable talkable = Test::new;
        talkable.talk("talk me..");
    }

}

interface Flyable
{
    void fly();
}

interface Talkable
{
    void talk(String arg);
}

```

As constructor in Java is a special method, method reference could be applied to it too with the help of new as a method name.
