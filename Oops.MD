# **DELEGATE**

A delegate can be seen as a placeholder for a/some method(s).

By defining a delegate, you are saying to the user of your class, " *Please feel free to assign any method that matches this signature to the delegate and it will be called each time my delegate is called* ".

Typical use is of course events. All the OnEventX *delegate* to the methods the user defines.

Delegates are useful to offer to the **user** of your objects some ability to customize their behavior. Most of the time, you can use other ways to achieve the same purpose and I do not believe you can ever be **forced** to create delegates. It is just the easiest way in some situations to get the thing done.

# EVENT

To understand event handlers, you need to understand delegates. In C#, you can think of a delegate as a pointer (or a reference) to a method. This is useful because the pointer can be passed around as a value.

The central concept of a delegate is its signature, or shape. That is (1) the return type and (2) the input arguments. For example, if we create a delegate void MyDelegate(object sender, EventArgs e), it can only point to methods which return void, and take an object and EventArgs. Kind of like a square hole and a square peg. So we say these methods have the same signature, or shape, as the delegate.

So knowing how to create a reference to a method, let's think about the purpose of events: we want to cause some code to be executed when something happens elsewhere in the system - or "handle the event". To do this, we create specific methods for the code we want to be executed. The glue between the event and the methods to be executed are the delegates. The event must internally store a "list" of pointers to the methods to call when the event is raised.* Of course, to be able to call a method, we need to know what arguments to pass to it! We use the delegate as the "contract" between the event and all the specific methods that will be called.

So the default EventHandler (and many like it) represents a specific shape of method (again, void/object-EventArgs). When you declare an event, you are saying which shape of method (EventHandler) that event will invoke, by specifying a delegate:

```
//This delegate can be used to point to methods
//which return void and take a string.
public delegate void MyEventHandler(string foo);

//This event can cause any method which conforms
//to MyEventHandler to be called.
public event MyEventHandler SomethingHappened;

//Here is some code I want to be executed
//when SomethingHappened fires.
void HandleSomethingHappened(string foo)
{
    //Do some stuff
}

//I am creating a delegate (pointer) to HandleSomethingHappened
//and adding it to SomethingHappened's list of "Event Handlers".
myObj.SomethingHappened += new MyEventHandler(HandleSomethingHappened);

//To raise the event within a method.
SomethingHappened("bar");


```

(*This is the key to events in .NET and peels away the "magic" - an event is really, under the covers, just a list of methods of the same "shape". The list is stored where the event lives. When the event is "raised", it's really just "go through this list of methods and call each one, using these values as the parameters". Assigning an event handler is just a prettier, easier way of adding your method to this list of methods to be called).

# **METHOD OVERLOADING AND METHOD OVERRIDING**

CT- Method Overloading

RT - Method Overriding

Method overloading deals with the notion of having two or more methods in the same class with the same name but different arguments.

void foo(int a)
void foo(int a, float b)

```
using System;


public class Program
{
    // Method overload for a single integer parameter
    public void Print(int a)
    {
        Console.WriteLine($"Integer: {a}");
    }

    // Method overload for an integer and a float parameter
    public void Print(int a, float b)
    {
        Console.WriteLine($"Integer: {a}, Float: {b}");
    }

    // Method overload for a single string parameter
    public void Print(string message)
    {
        Console.WriteLine($"Message: {message}");
    }

    public static void Main(string[] args)
    {
        Program ex = new Program();

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

# What is the difference between constant and readonly in C#

# Difference between the Equality Operator (==) and Equals() Method in C#

# What is Boxing and Unboxing in C#

# OUT AND REF

Declaring an out method is useful when you want a method to return multiple values. A method that uses an out parameter can still return a value. A method can have more than one out parameter.

The out keyword causes arguments to be passed by reference. This is similar to the ref keyword, except that ref requires that the variable be initialized before being passed. To use an out parameter, both the method definition and the calling method must explicitly use the out keyword.

Although variables passed as an out arguments need not be initialized prior to being passed, the calling method is required to assign a value before the method returns.

# IMPLICITLY AND EXPLICITLY VARIABLE

**implicitly**

var word = "ABC";

var num = 5;

**explicitly**

string word ="ABC";

int num =5;

# DATA HIDING

making the members of a class non-public

```
using System;

class BaseClass{

	public virtual void Method1(){
	Console.WriteLine("BaseClass M1");
	}

	public virtual void Method2(){
	Console.WriteLine("BaseClass M2");
	}
}

class DerivedClass: BaseClass{
	public override void Method1(){
	Console.WriteLine("DerivedClass M1");
	}

	public new void Method2(){
	Console.WriteLine("DerivedClass M2");
	}
}



public class Program
{
	public static void Main()
	{
		BaseClass b = new BaseClass();
		b.Method1();
		b.Method2();
	
		BaseClass c = new DerivedClass();
		c.Method1();
		c.Method2();
	
	}
}
```

# ACCESS MODIFIER

Protected:- members can be used in the derived classess, but they can't be used outside.
