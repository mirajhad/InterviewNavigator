# Contructor

using System;

class Employee{
public int Id, Age;
        public string Address, Name;
        public bool IsPermanent;
        //User Defined Default Constructor
        public Employee()
        {
            Id = 100;
            Age = 30;
            Address = "Bhubaneswar";
            Name = "Anurag";
            IsPermanent = true;
        }
        public void Display()
        {
            Console.WriteLine("Employee Id is:  " + Id);
            Console.WriteLine("Employee Age is:  " + Age);
            Console.WriteLine("Employee Address is:  " + Address);
            Console.WriteLine("Employee Name is:  " + Name);
            Console.WriteLine("Is Employee Permanent:  " + IsPermanent);
        }
}

public class Program
{
	public static void Main()
	{
		Employee e = new Employee();
		e.Display();
	}
}
