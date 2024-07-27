**DELEGATE**

A delegate can be seen as a placeholder for a/some method(s).

By defining a delegate, you are saying to the user of your class, " *Please feel free to assign any method that matches this signature to the delegate and it will be called each time my delegate is called* ".

Typical use is of course events. All the OnEventX *delegate* to the methods the user defines.

Delegates are useful to offer to the **user** of your objects some ability to customize their behavior. Most of the time, you can use other ways to achieve the same purpose and I do not believe you can ever be **forced** to create delegates. It is just the easiest way in some situations to get the thing done.
