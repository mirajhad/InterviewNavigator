# Mthod Syntax and Query Syntax

var evenNumbers = numbers

.Where(n => n % 2 ==0);

var evenNumbers = from number in numbers

    where number % 2 == 0

    select number;

# Deferred Execution

The evaluation of a LINQ expression id `delayed` until the value is actually needed. It allow us to work on latest data.

# First and FirstOrDefault

First() method returns first element in the collection that matches with the collection.

It throws exception if no element matches with the condition.

FirstOrDefault() method returns first element that matches with the condition.

It returns null if no element matches with the condition.

# Single and SingleOrDefault

It returns first element (only one element) that matches with the collection.

It throws exception if no element or multiple elements match with the condition.

SingleOrDefault

It returns first element (only one element) that matches with the collection.

It returns null if no element matches with the condition; but it throws exception if multiple elements match with the condition.
