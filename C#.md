# Value Type vs Reference Types

System.value

struct, int char

Syste,.Object

classes,delegate, string, array

# What is a managed and unmanaged code

Managed code lets you run the code on a managed CLR runtime environment in the .NET framework.
Unmanaged code is when the code doesn’t run on CLR, it is an unmanaged code that works outside the .NET framework.

# Garbage Collection

Garbage Collection is a process of deleting objects from memory, to free-up memory; so the same memory can be re-used

**When GC gets triggered?**

There are NO specific timings for GC to get triggered.

GC automatically gets trigged in the following conditions:

- When the "heap" is full or free space is too low.
- When we call GC.Collect() explicitly.

#### Generations in GC

Heap contains three segments (called generations):

* Generation 2 [Long-Lived Generation]
* Generation 1 [Survival Generation]
* Generation 0 [Short-Lived Generation]

# IDisposable

The "IDisposable" interface of "System" namespace, has a method called "Dispose", which is used to close un-managed resources that are created during the life-time of the object.

#### Using Declaration

You can prefix "using" keyword before the local variable declaration, in order to call "Dispose" method when that variable goes out of scope.

**Creating object**

<pre class="prettyprint linenums prettyprinted" role="presentation"><ol class="linenums"><li class="L0"><p><span class="kwd">public</span><span class="pln"></span><span class="kwd">void</span><span class="pln"></span><span class="typ">Method</span><span class="pun">(</span><span class="pln"></span><span class="pun">)</span></p></li><li class="L1" data-node-id="20240811143924-8sk6xs9"><p><span class="pun">{</span></p></li><li class="L2"><p><span class="pln"></span><span class="kwd">using</span><span class="pln"></span><span class="typ">ClassName</span><span class="pln"> referenceVariable </span><span class="pun">=</span><span class="pln"></span><span class="kwd">new</span><span class="pln"></span><span class="typ">ClassName</span><span class="pun">(</span><span class="pln"></span><span class="pun">);</span></p></li><li class="L3" data-node-id="20240811143924-9hjeuzn"><p><span class="pln"> </span></p></li><li class="L4"><p><span class="pln"></span><span class="com">//do work here</span></p></li><li class="L5" data-node-id="20240811143924-yfl589q"><p><span class="pln"> </span></p></li><li class="L6"><p><span class="pun">}</span><span class="pln"></span><span class="com">//Dispose will be called automatically here</span></p></li></ol></pre>

# Destructor

Destructor is a special method of the class, which is used to close un-managed resources (such as database connections and file connections), that are opened during the class execution.

# Base Keyword

The `base` keyword is used to refer to the base class when chaining constructors or when you want to access a member (method, property, anything) in the base class that has been overridden or hidden in the current class. For example,

```
using System;

public class Program
{
    class A {
        protected virtual void Foo() {
            Console.WriteLine("I'm A");
        }
    }

    class B : A {
        protected override void Foo() {
            Console.WriteLine("I'm B");
        }

        public void Bar() {
            Foo();       // Calls Foo() from class B
            base.Foo();  // Calls Foo() from class A
        }
    }

    public static void Main(string[] args)
    {
       new B().Bar();
    }
}

```

would output

```csharp
I'm B
I'm A
```
