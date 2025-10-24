## Single Delegates
This is a delegate that can only refer to one method at a time. Single Cast Delegates are used to refer to a single method with a matching signature. The system generates Single Cast Delegates. Delegate the class.

'''
namespace singledelegate
{
  public Delegate void delegate1(int a, int b);

  class program
  {
    public void addition(int a, int b)
    {
      Console.WriteLine("The sum is " + (a + b));
    }

    public void subtraction(int a, int b)
    {
      Console.WriteLine("The Difference is " + (a - b));
      Console.ReadKey();
    }
  }

  class Program
  {
    static void Main(string[] args)
    {
      program obj = new program();

      delegate1 d1 = new delegate(obj.addition);
      d1(100, 200);

      delegate1 d2 = new delegate(obj.subtraction);
      d2(100, 200);
    }
  }
}
'''
