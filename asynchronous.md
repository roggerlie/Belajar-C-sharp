## What is asynchronous programming ?
- Using asynchronous programming, the application can work on other tasks without waiting for the task to be completed.
- Asynchronous programming is very popular in C# thanks to the async and await keywords.
- When dealing with UI, we use long running method like reading a large file or something similiar.
- If any synchronous process is blocked, the entire application is blocked, and our application stops responding until the task is completed.
---

## Need of asynchronous programming
- In synchronous programming, compilers run one statement and wait for it to complete and then move to next one
- In asynchronous programming, compilers run one statement and while it gets completing, we will also work on the next one
---

## Async and await keyword

### Async Keyword
- Asynchronous methods are created by using the async modifier on a method.
- An async method runs synchronously until it reaches its first await operator, at which point it suspends.

### Await Keyword
- While the asynchronous operation is running, the await operator suspends the async method evaluation.
- When the asynchronous operation completes, the await operator returns the result.

If there is no await operator in the async method, the method executes synchronously.

```csharp
class Program
{

  static void Main(string[] args)
  {
    Method1();
    Method2();
    Console.ReadKey();
  }

  public static async Task Method1()
  {
    await Task.Run(() => {
      for(int i = 0; i < 100; i++;)
      {
        Console.WriteLine("Method 1 is running");
        Task.Delay(100).Wait();
      }
    });
  }

  public static void Method2()
  {
      for(int i = 0; i < 25; i++;)
      {
        Console.WriteLine("Method 2 is running");
        Task.Delay(100).Wait();
      }
  }
}
```

- Asynchronous programming is used for two kinds of tasks: I/O-bound tasks and CPU-bound tasks.
- Whereas synchronous programming allows us to run one tasks at a time.
- The async modifier is used on a method to create asynchronous methods.
- While the asynchronous operation is running, the await operator suspends the async method evaluation.
