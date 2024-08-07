# Mthod Syntax and Query Syntax

var evenNumbers = numbers

.Where(n => n % 2 ==0);


var evenNumbers = from number in numbers

    where number % 2 == 0

    select number;
