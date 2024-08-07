# Mthod Syntax and Query Syntax

var evenNumbers = numbers

.Where(n => n % 2 ==0);

var evenNumbers = from number in numbers

    where number % 2 == 0

    select number;

# Deferred Execution

The evaluation of a LINQ expression id `delayed` until the value is actually needed. It allow us to work on latest data.
