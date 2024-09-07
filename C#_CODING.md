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

---

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

---

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

---

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

---

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

## Count Occurance using Dictionary

```
using System;
using System.Collections.Generic;
public class Program
{
	public static void Main()
	{

		string input = "example string";
        	Dictionary<char, int> charCount = new Dictionary<char, int>();

        foreach (char c in input)
        {
            if (charCount.ContainsKey(c))
            {
                charCount[c]++;
            }
            else
            {
                charCount[c] = 1;
            }
        }

        foreach (var item in charCount)
        {
            Console.WriteLine($"{item.Key}: {item.Value}");
        }
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

```
using System;
using System.Collections.Generic;
using System.Linq;

public class Program
{
	public static void Main()
	{
		List<int> numbers = new List<int>{1,3,3,2,1};

		var occurances = numbers.GroupBy(x=>x)
			.Select(g => new{Number = g.Key, Count= g.Count()});

		foreach(var occ in occurances)
		{
			Console.WriteLine($"{occ.Number}={occ.Count}");
		}
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

## Factorial

```
if n = 0 return 1
else
return fact(n-1)*n
```

## Fibonacci

```
if n <= 1 return
else
return fib(n-1) + fib(n-1)
```

## Using string.Join

```
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        var list = new List<int> { 1, 2, 3, 4, 5 };

        // Print the list as a comma-separated string
        Console.WriteLine(string.Join(", ", list));
    }
}

```

## Reverse String

```
using System;

public class Program
{
	public static void Main()
	{
		string str = "miraaj";
		char[] charArray = str.ToCharArray(); 
  		for (int i = 0, j = str.Length - 1; i < j; i++, j--) 
  		{ 
      		charArray[i] = str[j]; 
      		charArray[j] = str[i]; 
  		} 
  		Console.WriteLine(charArray); 
	}
}
```

# Move zero at Last

```
using System;

public class Program
{
	public static void Main()
	{
	int[] A = { 5, 6, 0, 4, 6, 0, 9, 0, 8 }; 
        int n = A.Length; 
        int j = 0; 
        for (int i = 0; i < n; i++) { 
            if (A[i] != 0) { 
                int temp = A[j]; 
                A[j] = A[i]; 
                A[i] = temp; 
                j++; 
            } 
        } 
        for (int i = 0; i < n; i++) { 
            Console.WriteLine(A[i]); 
        } 
	}
}
```

# Check Big Letter

```
using System;
using System.Linq;
		
public class Program
{
	public static void Main()
	{
		string[] st= ["fox","ox","DOG"];
		var data = st.Any(x=>x.All(le => char.IsUpper(le)));
		Console.WriteLine(data);
	}
}
```

# Bubble Sort

```







using System;

public class Program
{
	public static void Main()
	{
		int[] arr =
		{
			800,
			11,
			50,
			771,
			649,
			770,
			240,
			9
		};
		int temp = 0;
		for (int i = 0; i < arr.Length; i++)
		{
			for (int j = 0; j < arr.Length - 1; j++)
			{
				if (arr[j] > arr[j + 1])
				{
					temp = arr[j];
					arr[j] = arr[j+1];
					arr[j+1] = temp;
				}
			}

			Console.Write("{0} ",arr[i]);
		}
	}
}
```

# Custom largest Number

```
using System;
				
public class Program
{
	public static void Main()
	{
		int[] ar=[9,1,2,3,4,4,];
		for(var i=0;i<ar.Length;i++){
		for(var j=0;j<ar.Length-1;j++){
			if(ar[j]<ar[j+1]){
				int temp=ar[j];
				ar[j]=ar[j+1];
				ar[j+1]=temp;
			}
		}
		}
		for(var i=0;i<ar.Length;i++){
		Console.WriteLine(ar[i]);
		}
	
		Console.Write("Enter your name: ");
		int name = Convert.ToInt32(Console.ReadLine());
		Console.WriteLine(ar[name-1]);
	}
}
```
