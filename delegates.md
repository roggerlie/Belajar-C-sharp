## Single Delegates
This is a delegate that can only refer to one method at a time. Single Cast Delegates are used to refer to a single method with a matching signature. The system generates Single Cast Delegates. Delegate the class.

### 🧩 Contoh Program Delegate Tunggal di C#

Program ini menunjukkan cara menggunakan **single delegate** di bahasa pemrograman **C#**.  
Delegate berfungsi seperti pointer ke method, sehingga kita bisa memanggil method secara dinamis melalui objek delegate.

---

### 📘 Penjelasan Singkat

- `Delegate1` adalah delegate yang menerima dua parameter `int`.
- `Calculator` memiliki dua method: `Addition` dan `Subtraction`.
- Di `Main()`, kita membuat dua instance delegate untuk memanggil masing-masing method.

---

### 🧠 Kode Lengkap

```csharp
namespace SingleDelegate
{
    public Delegate void Delegate1(int a, int b);

    class Calculator
    {
        public void Addition(int a, int b)
        {
            Console.WriteLine("The sum is " + (a + b));
        }

        public void Subtraction(int a, int b)
        {
            Console.WriteLine("The difference is " + (a - b));
            Console.ReadKey();
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Calculator obj = new Calculator();

            Delegate1 d1 = new Delegate1(obj.Addition);
            d1(100, 200);

            Delegate1 d2 = new Delegate1(obj.Subtraction);
            d2(100, 200);
        }
    }
}
```

## Multi Delegate
This is a kind of delegates that can refer to multiple methods that have the same signature at one time.

```csharp
namespace Delegate
{
    public Delegate void MultiDelegate(int a, int b);

    class Program
    {
        public void add(int a, int b)
        {
            Console.WriteLine("The Sum is " + (a + b));
        }

        public void sub(int a, int b)
        {
            Console.WriteLine("The difference is " + (a - b));
            Console.ReadKey();
        }
    }

    class A
    {
        static void Main(string[] args)
        {
            Program p1 = new Program();

            MultiDelegate Md1 = new MultiDelegate(p1.add);
            MultiDelegate Md2 = new MultiDelegate(p1.sub);
            Md1 = Md1 + Md2;
            Md1(100, 200);
        }
    }
}
```

## Generic Delegate
Generic Delegate was introduced in .NET 3.5 and does not require the delegate instance to be defined in order to invoke the methods.

### Func Delegate
In C#, the Func Generic Delegate is found in the System namespace. This delegate accepts one or more input parameters and returns a single output parameter. The final parameter is regarded as the return value.
In C#, you must use the Func Generic delegate whenever your delegate returns a value, whatever it takes any input.

### Action Delegate
In C#, the Action Generic Delegate can also be found in the System namespace. It accepts one or more parameters and returns null. This delegate can accept up to 16 input parameters of different or the same type.
When your delegate does not return any value, regardless of whether it takes any input parameters or not, you must use the.

### Predicate Delegate
In C#, the Predicate Generic Delegate can also be found in the System namespace. This delegate is used to validate the method's criteria and returns the result as a Boolean, either True or False. It only accepts one input parameter and always returns a Boolean value, which is required.
You must use the Predicate Generic Delegate in C# whenever your delegate returns a Boolean value by taking one input.

```csharp
namespace Delegate
{
    public class GD
    {
        static void Main(string[] args)
        {
            Func<int, float, double, double> object1 = new Func<int, float, double, double>(SumNumber1);
            double output = object1.invoke(10, 12.15f, 45.78);
            Console.WriteLine(output);

            Action<int, float, double> object2 = new Action<int, float, double>(SumNumber2);
            object2.invoke(20, 25.45f, 12.45);

            Predicate<string> object3 = new Predicate<string>(ChecktheLength);
            boll b = object3.invoke("Hello");
            Console.WriteLine(b);
            Console.ReadKey();
        }

        public static double SumNumber1(int number1, float number2, double number3)
        {
            return number1 + number2 + number3;
        }

        public static void SumNumber2(int number1, float number2, double number3)
        {
            Console.WriteLine(number1 + number2 + number3);
        }

        public static bool ChecktheLength(string name1)
        {
            if(name1.Length < 10)
                return true;
            return false;
        }
    }
}
```

## Delegates with Named and Anonymous Method
A named method can be associated with a delegate. When you use a named method to instantiate a delegate, the method is passed as a parameter, for example.
```csharp
// Declare a delegate
delegate void Delegate(int x);

// Define a named method
void method(int k) {/*...*/}

// Instantiate the delegate using the method as a parameter
Delegate d = obj.method;
```
This is accomplished using a named method

- Delegates build with a named can encapsulate either a static or an instance method.
- In earlier versions of C#, named methods were the only way to instantiated a delegate.
- However, if creating a new method is an unnecessary overhead, C# allows you to instantiate a delegate and immediately specify a code block that the delegate will process when called.
- A lambda expression or an anonymous method can be included in the block.

An anonymous method, as the name implies, is one that does not have a name. In C#, anonymous method can be defined with the delegate keyword and assigned to a variable of the delegate type.

```csharp
public delegate void display(int value);

static void Main(string[] args)
{
    display d1 = delegate(int v) {
        Console.WriteLine("Inside Anonimous method.", v);
    }

    d1(10);
}
```

Variables defined in an outer function can be accessed by anonymous methods.

```csharp
public delegate void display(int value);

static void Main(string[] args)
{

    int i = 10;
    display d1 = delegate(int v) {
        v += i;
        Console.WriteLine("Inside Anonimous method: {O}", v);
    }

    d1(10);
}
```

A lambda expression is an anonymous method for creating delegates or expression tree types. In 2007, microsoft introduced lambda Expression in C# 3.0. Many developers frequently confuse anonymous methods with lambda expressions.

```csharp
{
    namespace Delegate
    {
        public delegate void Delex(int number);

        class Program
        {
            static void Main(string[] args)
            {
                Delex Del = new Delex(delegate {
                    Console.WriteLine("This is the function");
                });
                Del(100);
            }
        }
    }
}
```

Limitation of an anonymous method
- It cannot include any jump statements such as goto, break, continue.
- It cannot access an outer method ref or out parameter.
- It cannot contain or access dangerous code.
- Ir cannot be used on the is operator left side.
