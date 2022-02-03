# .net
using System;<br>

namespace amicable_number<br>
{<br>
    class amicable_number<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.WriteLine("\n---- Amicable numbers-----\n");<br>
            Console.Write("\n enter the first number:");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\n enter the SECOND number:");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for(int i=1;i<num1;i++)<br>
            {<br>
                if(num1%i==0)<br>
                {<br>
                    sum1 += i;<br>
                }<br>
            }<br>
            for(int i=1;i<num2;i++)<br>
            {<br>
                if(num2%i==0)<br>
                {<br>
                    sum2 += i;<br>
                }<br>
            }<br>
            if (sum1 == num2 && sum2 == num1)<br>
            {<br>
                Console.WriteLine("\n the numbers {0} and {1} are amiciable.", num1, num2);<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("\n the numbers {0} and {1} are not amiciable.", num1, num2);<br>
            }<br>
        }<br>
    }<br>
}<br>
output:<br>
![image](https://user-images.githubusercontent.com/98145098/150479686-83570f87-b1e4-46b4-aa82-a8ebc18b773a.png)
![image](https://user-images.githubusercontent.com/98145098/150481026-c0d77744-60dc-4f23-86c3-8ef1115bb567.png)










using System;

namespace binary2<br>
{<br>
    class binary2<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int number, digit = 1;<br>

            Console.WriteLine("\n enter the number of lines:");

            number = Convert.ToInt32(Console.ReadLine());
            for (int i = 1; i <= number; i++)
            {
                for (int space = number - i; space > 0; space--)
                {
                    Console.Write(" ");
                }
                for (int j = 0; j < i; j++)
                {
                    Console.Write(digit + " ");
                    digit = (digit == 1) ? 0 : 1;
                }
                Console.Write("\n");
            }
        }
    }
}
    






















//C# pgm to implement Principle of Delegate// using System;
namespace Exercises
{
class Delegates
{
delegate string UppercaseDelegate(string input);
static string UppercaseFirst(string input)
{
char[] buffer = input.ToCharArray();
buffer[0] =char.ToUpper(buffer[0]);
return new string(buffer);
}
static string UppercaseLast(string input)
{
char[] buffer =input.ToCharArray();
buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);
return new string(buffer);
}
static string UppercaseALL(string input)
{
return input.ToUpper();
}
static void WriteOutput(string input, UppercaseDelegate del)
{
Console.WriteLine("iutput string:{0}", input);
Console.WriteLine("Output string:{0}", del(input));
}
static void Main()
{
WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));
WriteOutput("tom", new UppercaseDelegate(UppercaseLast));
WriteOutput("tom", new UppercaseDelegate(UppercaseALL));
Console.ReadLine();
}
}
}
Output
