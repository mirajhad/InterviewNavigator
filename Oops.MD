# **DELEGATE**

A delegate can be seen as a placeholder for a/some method(s).

By defining a delegate, you are saying to the user of your class, " *Please feel free to assign any method that matches this signature to the delegate and it will be called each time my delegate is called* ".

Typical use is of course events. All the OnEventX *delegate* to the methods the user defines.

Delegates are useful to offer to the **user** of your objects some ability to customize their behavior. Most of the time, you can use other ways to achieve the same purpose and I do not believe you can ever be **forced** to create delegates. It is just the easiest way in some situations to get the thing done.

# **METHOD OVERLOADING AND METHOD OVERRIDING**

Method overloading deals with the notion of having two or more methods in the same class with the same name but different arguments.

void foo(int a)
void foo(int a, float b)

```
public class Example
{
    public void Print(int a)
    {
        Console.WriteLine($"Integer: {a}");
    }    public void Print(int a, float b)
    {
        Console.WriteLine($"Integer: {a}, Float: {b}");
    }    public void Print(string message)
    {
        Console.WriteLine($"Message: {message}");
    }
}class Program
{
    static void Main()
    {
        Example ex = new Example();
        ex.Print(5);                // Calls Print(int a)
        ex.Print(5, 3.14f);         // Calls Print(int a, float b)
        ex.Print("Hello World!");   // Calls Print(string message)
    }
}
```

Method overriding means having two methods with the same arguments, but different implementations. One of them would exist in the parent class, while another will be in the derived, or child class.

```
public class BaseClass
{
    public virtual void Display()
    {
        Console.WriteLine("Display from BaseClass");
    }
}public class DerivedClass : BaseClass
{
    public override void Display()
    {
        Console.WriteLine("Display from DerivedClass");
    }
}class Program
{
    static void Main()
    {
        BaseClass obj = new DerivedClass();
        obj.Display();   // Calls Display() from DerivedClass
    }
}
```

# **INTERFACE**

An interface is a contract: An interface is an empty shell. There are only the signatures of the methods, which implies that the methods do not have a body. The interface can't do anything. It's just a pattern.

An abstract class is a class that is only partially implemented by the programmer. It may contain one or more abstract methods. An abstract method is simply a function definition that serves to tell the programmer that the method must be implemented in a child class.

# Struct and Class

A structure is a value type so it is stored on the stack, but a class is a reference type and is stored on the heap.

A structure doesn't support inheritance, and polymorphism, but a class supports both.

By default, all the struct members are public but class members are by default private in nature.

As a structure is a value type, we can't assign null to a struct object, but it is not the case for a class.
