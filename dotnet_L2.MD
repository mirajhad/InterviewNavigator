Q1. **What is the difference between a struct and a class in C#?**

**`Answer:`**

* **struct:** A value type that is typically used for small, lightweight data structures. When assigned to another variable, a copy of the value is created.
* **class:** A reference type that is used for more complex data structures. When assigned to another variable, both variables point to the same object in memory. In financial applications, structs are often used for small data structures like money or simple financial objects, where performance and memory management are crucial

Q2. **How do you handle concurrency in C#?**

**`Answer:`**
Concurrency in C# can be handled using several methods:

* **lock statement:** Used to ensure that only one thread can access a block of code at a time, preventing race conditions.
* **Monitor class:** Provides more advanced control over thread synchronization.
* **Task and async/await:** Used for handling asynchronous operations efficiently, which is common in financial systems that need to handle multiple requests or processes concurrently.
* **Concurrent Collections:** These are thread-safe collections that can be used for managing shared data across threads. In the financial industry, concurrency is important when handling multiple transactions simultaneously or when accessing shared resources like databases.

Q3. **Explain the concept of decimal type and its importance in financial applications.**

**`Answer:`**
The decimal type is a 128-bit data type designed for precise financial calculations. It is crucial in financial applications to avoid rounding errors caused by the limitations of floating-point arithmetic. It ensures accurate representation of values such as currency.

```
decimal price = 99.99m;  // 'm' suffix denotes decimal type
```

Q4. **What is LINQ, and how would you use it to query financial data?**

**`Answer:`**
**LINQ** (Language Integrated Query) allows you to query collections in C# in a more readable and concise way. It supports both in-memory collections and data sources like databases.
Example of querying financial data:

```
var highValueTransactions = transactions
    .Where(t => t.Amount > 10000)
    .OrderBy(t => t.Date)
    .Select(t => new { t.TransactionId, t.Amount });
```



Q5. **How do you ensure high performance when processing large volumes of financial transactions?**

**`Answer:`**
To ensure high performance in financial systems, several strategies can be employed:
**Efficient algorithms:** Use appropriate sorting, searching, and aggregation algorithms that minimize complexity.
**Parallelism and concurrency:** Use Task, async/await, or Parallel to process multiple transactions in parallel.
**Memory management:** Use value types like struct when appropriate and minimize heap allocations to reduce memory overhead.
**Caching:** Cache frequently used data, such as exchange rates or stock prices, to avoid repetitive database queries.
**Efficient I/O: **Optimize database queries and use batch processing for large transaction sets.

Q6. **What is the difference between async and await in C#?**

**`Answer:`**

* async: A modifier that you apply to a method to indicate it contains asynchronous operations. It allows you to use await inside the method.
* await: Used within an async method to pause the execution of the method until the asynchronous task is completed.

Q7. **How would you implement transaction handling in C# to ensure consistency and atomicity in a financial application?**

**`Answer:`**
In C#, transaction handling can be achieved using the `TransactionScope` class or `IDbTransaction` for database transactions. The `TransactionScope` ensures that a series of operations are either fully completed or fully rolled back in case of an error, maintaining atomicity and consistency.

```
using (var scope = new TransactionScope())
{
    // Perform operations
    // If all operations succeed, commit the transaction
    scope.Complete();
}
```

In financial applications, ensuring that all parts of a transaction (e.g., transferring money between accounts) are consistent is critical.


Q8. **What are extension methods in C#? How might they be useful in financial applications?**

**`Answer:`**
Extension methods allow you to add new methods to existing types without modifying their original implementation. You create them by defining a static method in a static class with the this keyword.
Example of an extension method for formatting monetary values:

```
public static class DecimalExtensions
{
    public static string ToCurrency(this decimal value)
    {
        return value.ToString("C");
    }
}
```

In financial applications, you might use extension methods to simplify common operations like formatting numbers, handling monetary calculations, or creating custom validations.

Q9. **What is the difference between IEnumerable and IQueryable in C#?**

**`Answer:`**

* IEnumerable: Represents a collection of data that can be iterated over. It is executed in-memory, meaning the data is fetched and processed in one go.
* IQueryable: Represents a queryable collection, often used with LINQ to query data from a data source (e.g., a database). The query is executed on the server, which can improve performance by reducing the amount of data retrieved. In financial applications, IQueryable is typically used when querying large datasets from a database, as it allows for efficient filtering and paging at the database level.

Q10. **Explain boxing and unboxing in C#. How might these concepts affect performance in financial applications?**

**`Answer:`**

* **Boxing** : The process of converting a value type (e.g., int) into a reference type (e.g., object).
* **Unboxing** : The process of converting a reference type back into a value type. Boxing and unboxing can introduce performance overhead due to memory allocation. In financial applications, where performance is critical, unnecessary boxing should be avoided by using value types directly.
