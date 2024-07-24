## String sort
```
using System;
using System.Linq;

class Program
{
    static void Main()
    {
        string ar1 = "1,2,1,4,2,1";
        var data = ar1.Split(',').Select(int.Parse).OrderBy(x => x).ToArray();
        Console.WriteLine(string.Join(",", data));
    }
}
```
___________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
```
using System;
using System.Linq;
using System.Collections.Generic;

public class HelloWorld
{
    public static void Main(string[] args)
    {
        List<int> numbers = new List<int> { 9, 3, 1, 6, 4, 8 };
        var sortedNumbers = numbers.OrderBy(x => x);
        Console.WriteLine(string.Join(" ", sortedNumbers));
    }
}
```
____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
## Remove Vowels
```
using System;
using System.Linq;
public class HelloWorld
{
    public static void Main(string[] args)
    {
        string vowels = "aeiou";
        string name = "Some Name with vowels";
        name = new string(name.Where(c => !vowels.Contains(c)).ToArray());
        Console.WriteLine (name);
    }
}
```
_________________________________________________________________________________________________________________________________________________________
## Remove Duplicate
```
using System;
using System.Linq;
					
public class Program
{
	public static void Main()
	{
		string originalString = "amanisaman";
		string newString = string.Join(" ", originalString.ToCharArray().Distinct());
		Console.WriteLine(newString);
	}
}
```
___________________________________________________________________________________________________________________________________________________
## Remove duplicate
```
using System;				
public class Program
{
	public static void Main()
	{
		string key="mirajahhhh";
		string result ="";
		foreach(var value in key){
			if(result.IndexOf(value) == -1){
				result += value;
			}			
		}
		Console.WriteLine(result);
	}
}
```
## Count occurance
```
using System;
					
public class Program
{
	public static void Main()
	{
		string source ="miraaj";
		int count = 0;
		foreach (char c in source) 
  		if (c == 'a') count++;
		Console.WriteLine(count);
	}
}
```
## Sum of digit
```
using System;
				
public class Program
{
	public static void Main()
	{
		int number = 123;
        int sum = 0;
        while (number > 0)
        {
            sum = sum+ number % 10;	 
            number =number/10;     
        }
        Console.WriteLine($"Sum of digits: {sum}");
	}
}
```
## Reverse digit
```
using System;
				
public class Program
{
	public static void Main()
	{
		int reversed = 0;
		int number = 12345;

        while (number > 0)
        {
            int digit = number % 10;       // Get the last digit
            reversed = reversed * 10 + digit;  // Append digit to reversed number
            number /= 10;                 // Remove the last digit
        }
        Console.WriteLine(reversed);
	}
}
```