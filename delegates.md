## Single Delegates
This is a delegate that can only refer to one method at a time. Single Cast Delegates are used to refer to a single method with a matching signature. The system generates Single Cast Delegates. Delegate the class.

### 🧩 Contoh Program Delegate Tunggal di C#

Program ini menunjukkan cara menggunakan **single delegate** di bahasa pemrograman **C#**.  
Delegate berfungsi seperti pointer ke method, sehingga kita bisa memanggil method secara dinamis melalui objek delegate.

---

## 📘 Penjelasan Singkat

- `Delegate1` adalah delegate yang menerima dua parameter `int`.
- `Calculator` memiliki dua method: `Addition` dan `Subtraction`.
- Di `Main()`, kita membuat dua instance delegate untuk memanggil masing-masing method.

---

## 🧠 Kode Lengkap

```csharp
using System;

namespace SingleDelegate
{
    public delegate void Delegate1(int a, int b);

    class Calculator
    {
        public void Addition(int a, int b)
        {
            Console.WriteLine("The sum is " + (a + b));
        }

        public void Subtraction(int a, int b)
        {
            Console.WriteLine("The difference is " + (a - b));
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

            Console.ReadKey();
        }
    }
}

