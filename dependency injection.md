## What is dependency injection
- It's a software design pattern that enables for loosely coupled software.
- DI is a great way to reduce tight coupling between software components.
- DI also enables us to better manage future changes and other complexity in our software.
- DI's goal is to make code more manageable.

## How to implement dependency injection

### Constructor Injection
- The constructor injection usually has only one parameterized constructor.
- There is no default constructor in constructor dependency.
- We need to pass the specified value during object creation.
- We can use the injection component anywhere within the class.

```csharp
namespace propertyinjection
{
  public interface text
  {
    void print();
  }

  class format : text
  {
    public void print()
    {
      Console.WriteLine("Subscribe to Simplilearn");
    }
  }

  public class constructorinjection
  {
    private text _text;
    public constructorinjection(text t1)
    {
      this._text = t1;
    }

    public void print()
    {
      _text.print();
    }
  }

  class constructor()
  {
    static void Main(string[] args)
    {
      constructorinjection cs = new constructorinjection(BinaryWriter format());
      cs.print();
      Console.ReadKey();
    }
  }
}
```

### Property Injection
- Property is typically used when we need parameter less constructor.
- It could work without changing the object state.

```csharp
public interface INotificationAction
{
  void ActOnNotification(string message);
}

class Simple
{
  INotificationAction task = null;
  public void notify(INotificationAction at, string messages)
  {
    this.task = at;
    task.ActOnNotification(messages);
  }
}

class EventLogWriter : INotificationAction
{
  public void ActOnNotification(string messages)
  {
    Console.WriteLine("Click on the Bell icon to get notifications");
  }
}

class Program
{
  static void Main(string[] args)
  {
    EventLogWriter elw = new EventLogWriter();
    Simple at = new Simple();
    at.notify(elw, "to log");
    Console.ReadKey();
  }
}
```

### Method Injection
- We only need to pass the dependency in the method when using method injection.
- We do not use constructor injection because it would create a dependent object every time that class is instantiated.

```csharp
namespace propertyinjection
{
  public interface Iset
  {
    void print();
  }

  public class servic : Iset
  {
    public void print()
    {
      Console.WriteLine("print......");
    }
  }

  public class client
  {
    private Iset _iset();

    public void run(Iset serv)
    {
      this._iset = serv;
      Console.WriteLine("Start");
      this._iset.print();
    }
  }

  class method
  {
    public static void Main(string[] args)
    {
      client cn = new client();
      cn.run(new servic());
      Console.ReadKey();
    }
  }
}
```

## Conclusion
- Dependency injection helps in reducing class coupling
- Dependency injection increases the reusability of code
- The dependency injection helps to improve code maintainability
- Dependency injection makes it feasible to conduct unit testing
