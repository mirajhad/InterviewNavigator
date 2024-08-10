# What are solid principles ?

S- Single responsibility - Each class should have single job/responsibility.
O - Open/Closed Principle. Classes must be open to extension but closed to modification.
L - Liskov principle - If class A is subtype of class B then, Class B should be able to replace Class A with out disrupting the behaviour of our program.
I - Interface segregation - Clients should not be forced to depend on methods that they do not use.
D - Dependency inversion - High level modules should not depend on low level modules. Both must depend on abstraction.

---

# What are DRY, YAGNI, KISS principles ?

DRY- Do not repeat yourself.
Avoid duplication. Makes the software more maintainable and less error-prone.

YAGNI - You are not going to need it.
Avoid unnecessary features/functionalities to the software. This helps software focussed on essential requirements and makes it more maintainable.

KISS: Keep the implementation simple,stupid.
Keeping the software design and implementation as simple as possible.
This make software more understandable,maintainable and testable.

---

---

# How to reverse the order of words in a given string

using System;
using System.Linq;

class Program
{
    static void Main()
    {
        string input = "Hello world how are you";
        string[] words = input.Split(' ');
        var reversedWords = words.Reverse();
        string reversedString = string.Join(" ", reversedWords);
        Console.WriteLine(reversedString);
    }
}
++++++++++++++++++++++++++++++++++++++++++++++++++
Reverse Word
using System;
using System.Linq;

class Program
{
    static void Main()
    {
        string word = "Hello";
        string reversedWord = new string(word.Reverse().ToArray());
        Console.WriteLine(reversedWord);
    }
}
++++++++++++++++++++++++++++++++++++++++++++++++
reverse only word
using System;
using System.Linq;

class Program
{
    static void Main()
    {
        string input = "Hello world how are you";
        string[] words = input.Split(' ');
        var reversedWords = words.Select(word => new string(word.Reverse().ToArray()));
        string reversedString = string.Join(" ", reversedWords);
        Console.WriteLine(reversedString);
    }
}

---

numbers.Insert(0, elementToAdd);
numbers.Add(1)'

 string s = "Foo";
 string paddedLeft = s.PadLeft(5);
// paddedLeft = "  Foo" (pads with spaces by default)
 string paddedRight = s.PadRight(6, '+'); // paddedRight = "Foo+++

 string myLongString = "Hello World!";
 string myShortString = myLongString.Right(6);  // "World!"
 string myLeftString = myLongString.Left(5);    // "Hello"
 string myMidString1 = myLongString.Left(4);    // "lo World"
 string myMidString2 = myLongString.Left(2,3);    // "ell

string HelloWorld = "Hello World";
 HelloWorld.StartsWith("Hello"); // true
 HelloWorld.StartsWith("Foo"); // false

 string first = "Hello ";
 string second = "World";
 Concat method, or (much easier) using the
 string concat = first + second; // concat = "Hello World"
 concat = String.Concat(first, second); // concat = "Hello World"

 DateTime dt = new DateTime(2016,08,01,18,50,23,230);
 var t = String.Format("{0:t}", dt); // "6:50 PM"                             ShortTime
 var d = String.Format("{0:d}", dt); // "8/1/2016"                            ShortDate
 var T = String.Format("{0:T}", dt); // "6:50:23 PM"                          LongTime
 var D = String.Format("{0:D}", dt); // "Monday, August 1, 2016"              LongDate
 var f = String.Format("{0:f}", dt); // "Monday, August 1, 2016 6:50 PM"      LongDate+ShortTime
 var F = String.Format("{0:F}", dt); // "Monday, August 1, 2016 6:50:23 PM"   FullDateTime
 var g = String.Format("{0:g}", dt); // "8/1/2016 6:50 PM"                    ShortDate+ShortTime
 var G = String.Format("{0:G}", dt); // "8/1/2016 6:50:23 PM"                 ShortDate+LongTime
 var m = String.Format("{0:m}", dt); // "August 1"                            MonthDay
 var y = String.Format("{0:y}", dt); // "August 2016"                         YearMonth
 var r = String.Format("{0:r}", dt); // "SMon, 01 Aug 2016 18:50:23 GMT"      RFC1123
 var s = String.Format("{0:s}", dt); // "2016-08-01T18:50:23"                 SortableDateTime
 var u = String.Format("{0:u}", dt); // "2016-08-01 18:50:23Z"

var year =       String.Format("{0:y yy yyy yyyy}", dt); // "16 16 2016 2016"  year
 var month =      String.Format("{0:M MM MMM MMMM}", dt); // "8 08 Aug August"  month
 var day =        String.Format("{0:d dd ddd dddd}", dt); // "1 01 Mon Monday"  day
 var hour =       String.Format("{0:h hh H HH}",     dt); // "6 06 18 18"       hour 12/24
 var minute =     String.Format("{0:m mm}",          dt); // "50 50"            minute
 var secound =    String.Format("{0:s ss}",          dt); // "23 23"            second
 var fraction =   String.Format("{0:f ff fff ffff}", dt); // "2 23 230 2300"    sec.fraction
 var fraction2 =  String.Format("{0:F FF FFF FFFF}", dt); // "2 23 23 23"       without zeroes
 var period =     String.Format("{0:t tt}",          dt); // "P PM"             A.M. or P.M.
 var zone =       String.Format("{0:z zz zzz}",      dt); // "+0 +00 +00:00"

---

# Return Type

Return View
Return partial View
Redirect
Redirect To Action
Return content
Return JSON
Return JavaScript
Return File

# Repository Pattern

Design Pattern to separate the data access layer from application

Provides Interface without exposing implementation

Helps create abstraction

## What is the difference between const and readonly in C#?

`const`: Can't be changed anywhere.

`readonly`: This value can only be changed in the constructor. Can't be changed in normal functions.

# FOR AND FOREACH

The foreach statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects. If you need to add or remove items from the source collection, use a [for](https://learn.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2008/ch45axte(v=vs.90)) loop.

If you are iterating through a collection of items, and do not care about the index values then foreach is more convenient, easier to write and safer: you can't get the number of items wrong.

If you need to process every second item in a collection for example, or process them ion the reverse order, then a for loop is the only practical way.

# EXTENSION METHODS

Extension method allow us to seemingly add methods to an existing type without modifying this type's source code.

They are static method, but they're called as if they were instance methods on the extended type.

```
namespace Polymorphism.Extensions
{
	public static class StringExtensions
	{
		public static int CountLines(this string input)=> input.Split(Environment.NewLine).Length;
	}
}
```

# CONVENTIONAL AND ATTRIBUTE ROUTING

Following are some suggestions on when to use each one. Consider choosing traditional routes when:

You want centralized configuration of all your routes.
You use custom constraint objects.
You have an existing working application you don't want to change
Consider choosing attribute routes when:

You want to keep your routes together with your action's code
You are creating a new application or making significant changes to an existing.
You want to match route parameter names with an actual parameter of the method(action), this will make the route parameter more descriptive and omit the weird error where the route ID would not match and that usually happens because we didn't configure routing correctly and we were using asp.net default route.
But the reasons why many developers recommend the Attribute Routes is because it allows you quite a bit more flexibility and places the routes next to the actions that will actually use them. You can switch from option to another at any time is not difficult

Attribute Routing
Problems in Conventional Routing

Very difficult to understand for the developers, which route is for which action methods.

Very difficult to avoid conflicts among the routes [some times, we can't apply constraints].

Overall, some routes for multiple action methods; some routes for specific action methods; Overall, it looks cumbersome.

RouteConfig.cs

protected static void RegisterRoutes( RouteCollection routes)
{
   routes.MapRoute("name", "url", defaults, constraints);
   routes.MapRoute("name", "url", defaults, constraints);
   routes.MapRoute("name", "url", defaults, constraints);
   …
}

Types of URL Routing
Conventional Routing

It is the traditional way of routing.  routes.MapRoute( "name", "url", { defaults } )

Applicable for a specific / multiple action methods.

Routes will be cumbersome.

Enabled by default.

Supports parameters & constraints.

Attribute Routing

1. New and preferred way of routing:

["url"]
public ActionResult Methodname( )
{
}
2. Applicable for specific action method. Each action method must have "Route" defined.

3. Routes are very clearly understandable for the developers.
4. Should be enabled using:  routes.MapMvcAttributesRoutes( );
5. Also supports parameters & constraints.

# What is the use of @Html.AntiForgeryToken()?

Let's assume you have a register functionality in your web app. You have an AccountController (example.com/account/register) where you expect people to submit their info. Normally before someone posts the registration information needs to visit the actual (example.com/account/register) than submit the form.

Let say I am a bad guy and I want to flood your server with junk info all I need to do is just keep posting directly to (example.com/account/register) without visiting your site. So in order to stop me you implement AntiForgeryToken so you can make it sure I visited the page before I submitted the registration information.

CSRF / XSRF (Cross Site Request Forgery) is a process of sending a request to actual website, from a page present in attacker website, based on the logged-in session of actual website user.


#### How to Implement CSRF Security?

**View**

`@Html.AntiForgeryToken( )`

**Controller**

<pre class="prettyprint linenums prettyprinted" role="presentation"><ol class="linenums"><li class="L0"><p><span class="pun">[</span><span class="typ">ValidateAntiForgeryToken</span><span class="pun">]</span></p></li><li class="L1" data-node-id="20240810195432-c52y22a"><p><span class="kwd">public</span><span class="pln"></span><span class="typ">ActionResult</span><span class="pln"></span><span class="typ">Method</span><span class="pun">(</span><span class="pln"></span><span class="pun">)</span></p></li><li class="L2"><p><span class="pun">{</span></p></li><li class="L3" data-node-id="20240810195432-p1f8zmf"><p><span class="pun">}</span></p></li></ol></pre>

# Performance Optimization

Bundling and Minification
Used to load multiple css files / js files with a single request.

Also minifies (compresses) the css / js files.

Types of Bundles:

ScriptBundle: Contains javascript files (.js files).

StyleBundle: Contains css fles (.css files).

Microsoft.AspNet.Web.Optimization

This NuGet Package needs to be installed in the project, to use bundling concept.

# Strongly Typed Views

View that is associated to a specific model class is called as "Strongly Typed View".

Strongly typed views have to specify the model class name with @model directive at the top of the view.

Strongly Typed Views can receive model objects from the controller.

To receive model collections from the controller: `@model List<modelClassNameHere>`

# HTML Helpers

* Binds HTML elements to Model Properties.
* Pre-defined methods that execute on server and generate (render) a specific html tag at run time.
* @Html is an object of HtmlHelper class.

**Server code:**

`@Html.TextBoxFor (model => model.EmpName)`

**Browser (Client) - auto generated**

<pre class="prettyprint linenums prettyprinted" role="presentation"><ol class="linenums"><li class="L0"><p><span class="tag"><input</span><span class="pln"></span><span class="atn">type</span><span class="pun">=</span><span class="atv">"text"</span><span class="pln"></span><span class="atn">name</span><span class="pun">=</span><span class="atv">"EmpName"</span><span class="tag">></span></p></li></ol></pre>

#### List of HTML Helpers

1. **Html.ActionLink:**      Hyperlink
2. **Html.TextBoxFor: **    Textbox
3. **Html.TextAreaFor:**   TextArea
4. **Html.CheckBoxFor: **   CheckBox
5. **Html.RadioButtonFor: **  RadioButton
6. **Html.DropDownListFor:**    Dropdown
7. **Html.ListBoxFor:**    Multi-Select ListBox
8. **Html.HiddenFor: **   Hidden Field
9. **Html.PasswordFor: **  Password TextBo
10. **Html.DisplayFor: **   Plain text
11. **Html.LabelFor: **   Label
12. **Html.EditorFor: **  TextBox /    TextArea / Numeric TextBox / Date TextBox etc.
