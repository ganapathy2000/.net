# .net
1.C# program to check whether the entered number is Amicable number/not :
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








2.C# program to print a binary triangle:

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
    
output:




![binary](https://user-images.githubusercontent.com/98145098/152476808-80244538-3ab1-4d63-a704-0522804433a8.png)











3.C# program to implement Principle of Delegate input strings to uppercase first,last and enter string:
using System;<br>
 namespace Exercises<br>
{<br>
    class Delegates<br>
    {<br>
        delegate string UppercaseDelegate(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[0] =char.ToUpper(buffer[0]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        {<br>
            char[] buffer =input.ToCharArray();<br>
            buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseALL(string input)<br>
        {<br>
            return input.ToUpper();<br>
        }<br>
        static void WriteOutput(string input, UppercaseDelegate del)<br>
        {<br>
            Console.WriteLine("iutput string:{0}", input);<br>
            Console.WriteLine("Output string:{0}", del(input));<br>
        }<br>
        static void Main()<br>
        {<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseLast));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseALL));<br>
            Console.ReadLine();<br>
        }<br>
 }<br>
}<br>
Output

![Screenshot 2022-02-04 101346](https://user-images.githubusercontent.com/98145098/152473212-7ad29f57-deca-42fb-a403-838c5a028b10.png)





4.C# program  that bench marks 2D jagged array allocation using system:
    using System;<br>
using System.Diagnostics;<br>
namespace array<br>
{<br>
    class Benchmarkallocation<br>
        {<br>
        const int max= 100000;<br>
    static void Main(string[] args)<br>
    {<br>
        var Arr2D = new int[100, 100];<br>
        var ArrJagged = new int[100][];<br>
        for (int i = 0; i < 100; i++)<br>
        {<br>
            ArrJagged[i] = new int[100];<br>
        }<br>
        var Stopwatch2D = Stopwatch.StartNew();<br>
        for (int i = 0; i < max; i++)<br>
        {<br>
            for (int j = 0; j < 100; j++)<br>
            {<br>
                for (int k = 0; k < 100; k++)<br>
                {<br>
                    Arr2D[j, k] = k;<br>
                }<br>
            }<br>
        }<br>
        Stopwatch2D.Stop();<br>
        var StopwatchJagged = Stopwatch.StartNew();<br>
        for (int i = 0; i < max; i++)<br>
        {<br>
            for (int j = 0; j < 100; j++)<br>
            {<br>
                for (int k = 0; k < 100; k++)<br>
                {<br>
                    ArrJagged[j][k] = k;<br>
                }<br>
            }<br>
        }<br>
        StopwatchJagged.Stop();<br>
        Console.Write("\n time taken for allocation in case of 2D array:");<br>
        Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "milliseconds");<br>
        Console.Write("\n time taken for allocation in case of jagged array:");<br>
        Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");<br>
    }<br>
}<br>
}<br>
Output:




![Screenshot 2022-02-04 101746](https://user-images.githubusercontent.com/98145098/152473528-3d20d302-aad3-4ce8-8c80-da4081fcbb56.png)




5.C# program to generate reg num automatically for 100 Students using static constructor:
using System;<br>
namespace Exercises<br>
{<br>
    class RegisterNum<br>
    {<br>
        int regNo;<br>
        static int startNum;<br>
        static  RegisterNum()<br>
        {<br>
            startNum = 20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
        regNo=++startNum;<br>
        }<br>
        public static void Main(String[] args)<br>
        {<br>
            for(int i=0;i<100;i++)<br>
            {<br>
                RegisterNum Student = new RegisterNum();<br>
                Console.WriteLine("student{0}:{1}", i+1, Student.regNo);<br>
                    }<br>
        }<br>
    }<br>
}<br>

Output:


![Screenshot 2022-02-04 102226](https://user-images.githubusercontent.com/98145098/152473990-3b118e43-aef4-44aa-8279-48f6b6f4c6be.png)



6.C# program to print "is" in a given sentences:
using System;<br>
namespace Exercises<br>
{<br>
    class FrequencyIS<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int count=0;<br>
            string inputString;<br>
            Console.WriteLine("\n ------Frequency of Word is-------");<br>
            Console.Write("\n Enter the input string:");<br>
            inputString=Console.ReadLine();<br>
            char[] separator ={',', ' ', '.' , '!', '\n'};<br>
            string testString=inputString.ToLower();<br>
            String[] outcomes=testString.Split(separator)<br>;
            foreach(String s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s=="is")<br>
                    count++;<br>
            }<br>
            Console.WriteLine("\n Number of 'is' in'"+ inputString +"' is :" + count);<br>
            }<br>
        }<br>
    }<br>
    Output:
    
    
    
   ![frequency](https://user-images.githubusercontent.com/98145098/152474434-5558a61b-f7d0-4b40-a4c9-108d02a4da57.png)


    
    
    
    
 7.C# program to find sum of values of Diagonal for matrix:
 using System;<br>
namespace Exercises<br>
{<br>
    class SumOfDiagonals<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int MaxRow, MaxCol, Sum = 0;<br>
            int[,] Matrix;<br>
            Console.WriteLine("\n SUM OF DIAGONAL OF A MATRIX \n");<br>
            Console.Write("\nEnter the number of rows:");<br>
            MaxRow = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\nEnter the number of columns:");<br>
            MaxCol = Convert.ToInt32(Console.ReadLine());<br>
            if (MaxRow != MaxCol)<br>
            {<br>
                Console.WriteLine("\nThe Dimensions entered are not of Square Matrix:");<br>
                Console.WriteLine("\nExiting the Program..");<br>
                return;<br>
            }<br>
            Matrix = new int[MaxRow, MaxCol];<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {<br>
<br>
                for (int j = 0; j < MaxCol; j++)<br>
                {<br>
                    Console.Write("\n Enter the ({0},{1})th element of the matrix:", (i + 1), (j + 1));<br>
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
                }<br>
            }<br>
            Console.WriteLine("\nThe entered Matrix is:");<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {<br>
                for (int j = 0; j < MaxCol; j++)<br>
                {<br>
                    Console.Write(" " + Matrix[i, j]);<br>
                    if (i == j)<br>
                    {<br>
                        Sum += Matrix[i, j];<br>
                    }<br>
                }<br>
                Console.WriteLine();<br>
            }<br>
            Console.WriteLine("\nThe Sum of Diagonal is " + Sum);<br>
        }<br>
    }<br>
}<br>
    
    Output:
    
    
   ![matrix](https://user-images.githubusercontent.com/98145098/152479789-751cccd1-8697-499c-99ac-9d124d5a79b4.png)



   
   
   
   
    
  
 8.c# program to create a gray code: 
  using System;
namespace Exercises<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n^(n>>1);<br>

        }
        static void Main (string[]args)
        {
            int inputNum,GrayNum;
            Console.Write("\n Enter Decimal no:");
            inputNum = Convert.ToInt32(Console.ReadLine());

            Console.WriteLine("\n Binary equivalent of {0} :{1} " ,inputNum,
                Convert.ToString(inputNum,2));

            GrayNum=getGray(inputNum);
            Console.WriteLine("\n Binary equivalent of {0} :{1} ", inputNum,
               Convert.ToString(GrayNum, 2));
        }


    }
}

Output:


![gray](https://user-images.githubusercontent.com/98145098/152475429-5c923dd0-4e45-4703-8bf4-50ec77c0f101.png)




9.c# program using multilevel inheritance with virtual methods(displaying student details):

using System;<br>
namespace Exercises<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {<br>
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void Display()<br>
        {<br>
            Console.WriteLine("\n-------- PERSONAL DETAILS --------\n");<br>
            Console.WriteLine("Name : " + name);<br>
            Console.WriteLine("Age : " + age);<br>
            Console.WriteLine("Gender : " + gender);<br>
        }<br>
    }<br>
    class CourseDetails : PersonalDetails<br>
    {<br>
        int regNo;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)<br>
        {<br>
            this.regNo = regNo;<br>
            this.course = course;<br>
            this.semester = semester;<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n-------- COURSE DETAILS --------\n");<br>
            Console.WriteLine("Register Number : " + regNo);<br>
            Console.WriteLine("Course : " + course);<br>
            Console.WriteLine("Semester : " + semester);<br>
        }<br>
    }<br>
    class MarksDetails : CourseDetails<br>
    {<br>
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age, gender, regNo, course, semester)<br>
        {<br>
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            {<br>
                this.marks[i] = marks[i];<br>
                total += marks[i];<br>
                if (marks[i] < 35)<br>
                {<br>
                    flagFail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
        private void Calculate()<br>
        {<br>
            average = total / 5;<br>
            if (flagFail == 1 || average < 40)<br>
                grade = "Fail";<br>
            else if (average >= 70)<br>
                grade = "Distinction";<br>
            else if (average >= 60)<br>
                grade = "First Class";<br>
            else if (average >= 50)<br>
                grade = "Second Class";<br>
            else<br>
                grade = "Pass Class";<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n-------- MARKS DETAILS --------\n");<br>
            Console.Write("Marks in 5 subjects: ");<br>
            for (int i = 0; i < 5; i++)<br>
                Console.Write(marks[i] + " ");<br>
            Console.WriteLine();<br>
            Console.WriteLine("Total : " + total);<br>
            Console.WriteLine("Average : " + average);<br>
            Console.WriteLine("Grade : " + grade);<br>
        }<br>
    }<br>
    class MultiLevel<br>
    {<br>
        public static void Main(string[] args)<br>
        {<br>
            MarksDetails Student1 = new MarksDetails("abhi", 21, "Male", 20190001, "MSc", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            Student1.Display();<br>
        }<br>
    }<br>
}<br>


Output:


![multi](https://user-images.githubusercontent.com/98145098/152476402-3e3f76ab-9958-4b4d-9d56-8c7024f1dff3.png)



10.c# program to calculate volume of 2 boxes and find resulant volume after addition of 2 boxes by implementing operator overloading :


using System;<br>
<br>
namespace Exercises<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>
<br>
        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
<br>
        public Box(float width, float height, float length)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = length;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
<br>
        public override string ToString()<br>
        {<br>
            return "box with width " + width + ",height " + height + " and length " + length;<br>
        }<br>
    }<br>
<br>
        class OperatorOverloading<br>
        {<br>
            public static void Main()<br>
            {<br>
                Box box1 = new Box(10, 20, 30);<br>
                Box box2 = new Box(25, 32, 15);<br>
<br>
                Console.WriteLine("Volume of {0} is {1}", box1, box1.Volume);<br>
                Console.WriteLine("Volume of {0} is {1}", box2, box2.Volume);<br>
                Console.WriteLine("Volume after adding boxes: {0}",box1+box2);<br>
<br>
            }<br>
        }<br>
}<br>

Output:

![box](https://user-images.githubusercontent.com/98145098/152478631-f5476206-e625-42c0-9eb6-296ab66007c7.png)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
11)//c# pgm to create a file , Check the existence of a file//<br>
using System;<br>
using System.IO;<br>
namespace Exercise<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string fileName;<br>
            while (true)<br>
            {<br>
                Console.WriteLine("\n.......MENU......\n");<br>
                Console.WriteLine("\n1.Create a File");<br>
                Console.WriteLine("\n2.Existence of the File");<br>
                Console.WriteLine("\n3.Read the contents of the File");<br>
                Console.WriteLine("\n4.Exit");<br>
                Console.WriteLine("\nEnter your choice:");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                {<br>
                    case 1:<br>
                        Console.Write("\nEnter the file name to create:");<br>
                        fileName = Console.ReadLine();<br>
                        Console.WriteLine("\nWrite the Contents to the File:\n");<br>
                        string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr = File.CreateText(fileName))<br>
                        {<br>
                            fileStr.WriteLine(r);<br>
                        }<br>
                        Console.WriteLine("File is Created...");<br>
                        break;<br>
                    case 2:<br>
                        Console.Write("\nEnter the file name:");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            Console.WriteLine("File exits...");<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exits in the current directory!");<br>
                        }<br>
                        break;<br>
                    case 3:<br>
                        Console.Write("Enter the file name to read the contents:\n");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(fileName))<br>
                            {<br>
                                string s = "";<br>
                                Console.WriteLine(" Here is the content of the file : ");<br>
                                while ((s = sr.ReadLine()) != null)<br>
                                {<br>
                                    Console.WriteLine(s);<br>
                                }<br>
                                Console.WriteLine("");<br>
                            }<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exists");<br>
                        }<br>
                        break;<br>
                    case 4:<br>
                        Console.WriteLine("\n Exiting...");<br>
                        return;<br>
                    default:<br>
                        Console.WriteLine("\n Invalid choice");<br>
                        break;<br>
            }<br>
        }<br>
    }<br>
}<br>
Output:
![exis 1](https://user-images.githubusercontent.com/98145098/155656455-747de1b4-6e06-422d-bff5-de1627e55f93.png)<br>
![exis 2](https://user-images.githubusercontent.com/98145098/155656437-092b382e-c229-40dd-9f59-2ddeea9ffd50.png)<br>
![exis 3](https://user-images.githubusercontent.com/98145098/155656402-b60e8410-92d5-4323-b856-ab4b3e740dda.png)<br>
![exis 4](https://user-images.githubusercontent.com/98145098/155656384-9e3f6bec-0002-4706-af13-4deb9d659c65.png)<br>
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ <br>
12)//C# Program to Perform File Comparison.//<br>
using System;<br>
using System.IO;<br>
namespace Exercises<br>
{<br>
 class FileRead<br>
 {<br>
 public static void Main()<br>
 {<br>
 string file1;<br>
 string file2;<br>
 Console.Write("Enter the first file path:");<br>
 file1 = Console.ReadLine();<br>
 Console.Write("Enter the second file path:");<br>
 file2 = Console.ReadLine();<br>
 if (!File.Exists(file1))<br>
 {<br>
 Console.WriteLine("First file does not exist!");<br>
 }<br>
 else if (!File.Exists(file2))<br>
 {<br>
 Console.WriteLine("Second file does not exist!");<br>
 }<br>
 else if (File.ReadAllText(file1) == File.ReadAllText(file2))<br>
 {<br>
 Console.WriteLine("Both files contain the same content");<br>
 }<br>
 else<br>
 {<br>
 Console.WriteLine("Contents of files are not same");<br>
 }<br>
 }<br>
 }<br>
}<br>


Output:<br>
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
13)//C# Program to Implement IComparable Interface// <br>
 using System;<br>
namespace Exercises<br>
{<br>
    class Fraction : IComparable<br>
    {<br>
        int z, n;<br>
        public Fraction(int z, int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator +(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public static Fraction operator *(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br>
            if ((float)z / n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
                return 1;<br>
            else<br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
        }<br>
    }<br>
    class ICompInterface<br>
    {<br>
        public static void Main()<br>
        {<br>
        Fraction[] a = {<br>
                        new Fraction(5,2),<br>
                        new Fraction(29,6),<br>
                        new Fraction(4,5),<br>
                        new Fraction(10,8),<br>
                        new Fraction(34,7)<br>
 };<br>
            Array.Sort(a);<br>
            Console.WriteLine("Implementing the IComparable Interface in " + "Displaying  Fractions: ");<br>
        foreach (Fraction f in a)<br>
            {<br>
                Console.WriteLine(f + " ");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
}<br>

Output:
![Ic interface](https://user-images.githubusercontent.com/98145098/155656852-e7bf1bab-19be-481f-81bb-6a94480fe7f7.png)

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
14)//c# pgm to create Thread Pools//<br>
using System;<br>
using System.Threading;<br>
namespace Exercises<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread1 is executing");<br>
            }<br>
        }<br>
        public void ThreadFun2(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
                Console.WriteLine("Thread 2 is executing");<br>
        }<br>
        public static void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
            for (int i = 0; i < 2; i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>
            }<br>
            Console.ReadKey();<br>
        }<br>
    }<br>
}<br>
OUTPUT:![Thread](https://user-images.githubusercontent.com/98145098/155656726-01cd3ea6-6a8b-447d-8041-2881f6e5c087.png)
<br>


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
15 //c# pgm to demonstrate error handling using try , catch and finally block//<br>
using System;<br>
namespace Exercises<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Age a = new Age();<br>
            try<br>
            {<br>
                a.displayAge();<br>
            }<br>
            catch (AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeException: {0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Execution of Finally block is done.");<br>
            }<br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException(string message) : base(message)<br>
    {<br>
    }<br>
}<br>
public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if (age < 0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is: {0}", age);<br>
        }<br>
    }<br>
}<br>
Output:
![error handling](https://user-images.githubusercontent.com/98145098/155656792-fbd762be-2eed-4328-9ac6-36e0e32b5f64.png)

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
16.C# program to find fibonacci:
using System;

public class FibonacciExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n1 = 0, n2 = 1, n3, i, number;<br>
        Console.Write("Enter the number of elements: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        Console.Write(n1 + " " + n2 + " "); //printing 0 and 1<br>    
        for (i = 2; i < number; ++i) //loop starts from 2 because 0 and 1 are already printed<br>    
        {<br>
            n3 = n1 + n2;<br>
            Console.Write(n3 + " ");<br>
            n1 = n2;<br>
            n2 = n3;<br>
        }<br>
    }<br>
}<br>


Output:

![image](https://user-images.githubusercontent.com/98145098/156500796-9c1c5bbc-0638-41eb-9b52-2814d53ada42.png)


17.**C# program to check whether entered number is prime or not**<br>
using System;<br>
public class PrimeNumberExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i, m = 0, flag = 0;<br>
        Console.Write("Enter the Number to check Prime: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        m = n / 2;<br>
        for (i = 2; i <= m; i++)<br>
        {<br>
            if (n % i == 0)<br>
            {<br>
                Console.Write("Not is not Prime.");<br>
                flag = 1;<br>
                break;<br>
            }<br>
        }<br>
        if (flag == 0)<br>
            Console.Write("Number is Prime.");<br>
    }<br>
}<br>

**Output**<br>
![image](https://user-images.githubusercontent.com/98141713/155660567-d6e5c053-4a8e-4a4f-8a20-5bffba3bde58.png)<br>
![image](https://user-images.githubusercontent.com/98141713/155660665-e448aef8-82f2-4252-84de-7905bc161e05.png)<br>


18.**C# program to check whethe the entered number is palindrome or not.**<br><br>

using System;<br>
public class PalindromeExample<br>
{<br><br>
    public static void Main(string[] args)<br>
    {<br>
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the Number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = (sum * 10) + r;<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)<br>
            Console.Write("Number is Palindrome.");<br>
        else<br>
            Console.Write("Number is not Palindrome");<br>
    }<br>
}<br>

**Output**<br>
![image](https://user-images.githubusercontent.com/98141713/155661626-d0438f5e-ea44-49a0-ac02-b503253a037b.png)<br>
![image](https://user-images.githubusercontent.com/98141713/155661756-d96a69ee-f912-4ab1-ae5d-ea00f975d43d.png)<br>

19.**C# program to find the factorial of the number**<br>

using System;<br>
public class FactorialExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int i, fact = 1, number;<br>
        Console.Write("Enter any Number: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        for (i = 1; i <= number; i++)<br>
        {<br>
            fact = fact * i;<br>
        }<br>
        Console.Write("Factorial of " + number + " is: " + fact);<br><br>
    }<br>
}<br>

**Output**<br>
![image](https://user-images.githubusercontent.com/98141713/155662479-c356c2e3-f20f-45ca-a7be-88306b2b0e90.png)<br>

20.**C# program to check the armstrong number**<br>

using System;<br>
public class ArmstrongExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the Number= ");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = sum + (r * r * r);<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)<br>
            Console.Write("Armstrong Number.");<br>
        else<br>
            Console.Write("Not Armstrong Number.");<br>
    }<br>
}<br>

**Output**<br>
![image](https://user-images.githubusercontent.com/98141713/155665893-e0365ce6-0844-4227-90b9-55f023170d69.png)<br>
![image](https://user-images.githubusercontent.com/98141713/155665984-5cc2ffd2-bf88-4722-a31a-835727e4d048.png)<br>

21.**C# program to check the sum of the numbers**<br>

using System;<br>
public class SumExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, sum = 0, m;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n > 0)<br>
        {<br>
            m = n % 10;<br>
            sum = sum + m;<br>
            n = n / 10;<br>
        }<br>
        Console.Write("Sum is= " + sum);<br>
    }<br>
}<br>

**Output**<br>
![image](https://user-images.githubusercontent.com/98141713/155667382-eb0a3d88-88ff-4613-85dc-8fda7124a346.png)<br>


22.**C# program to reverese a number**<br>

using System;<br>
public class ReverseExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, reverse = 0, rem;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n != 0)<br>
        {<br>
            rem = n % 10;<br>
            reverse = reverse * 10 + rem;<br>
            n /= 10;<br>
        }<br>
        Console.Write("Reversed Number: " + reverse);<br>
    }<br>
}<br>

**Output**<br>
![image](https://user-images.githubusercontent.com/98141713/155668185-182d6c4a-f5c3-414d-befe-998c5e3a4b05.png)<br>


