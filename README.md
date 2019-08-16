<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>C# Basics - Console Application</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
    <link rel="stylesheet" href="css/style.css">
    <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.15.9/styles/default.min.css">
    <script src="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.15.9/highlight.min.js"></script>
    <script>hljs.initHighlightingOnLoad();</script>
</head>
<body>
    <div class="header">
        <div class="container">
            <h1>C# Basics - Console Application</h1>
        </div>
    </div>
    <div class="main">
        <div class="container">
            <h2>INPUT AND OUTPUT</h2>
            <pre><code class="csharp">
using System;

namespace MyProject.Examples
{
    class ExampleOne
    {
        static void Main()
        {
            Console.Write("Enter 1st food name: ");
            string name1 = Console.ReadLine();
            int price1 = int.Parse(Console.ReadLine());

            Console.Write("Enter 2nd food name: ");
            string name2 = Console.ReadLine();
            int price2 = int.Parse(Console.ReadLine());

            int total = price1 + price2;

            Console.WriteLine("Total price of {0} and {1} is {2}",name1,name2,total);
            Console.Write("Total price of "+ name1 + " and "+name2+ " is "+total);
            Console.ReadKey();
        }
    }
}
            </code></pre>
            <div class="output">Enter 1st food name: Rice<br/>20<br/>Enter 2nd food name: Dal<br/>30<br/>Total price of Rice and Dal is 50<br/>Total price of Rice and Dal is 50<br/></div>

            <h2>DATA TYPES</h2>
<table class="table table-striped table-hover table-condensed table-bordered">
<tbody>
<tr>
<td><strong>Reserved Word</strong>
</td>
<td><strong>Type</strong>
</td>
<td><strong>Size (bits)</strong>
</td>
<td><strong>Range (values)</strong>
</td>
<td><strong>Default Value</strong>
</td>
</tr>
<tr>
<td><strong>byte</strong>
</td>
<td>Unsigned integer
</td>
<td>8
</td>
<td>0 to 255
</td>
<td>0
</td>
</tr>
<tr>
<td><strong>sbyte</strong>
</td>
<td>Signed integer
</td>
<td>8
</td>
<td>-128 to 127
</td>
<td>0
</td>
</tr>
<tr>
<td><strong>short</strong>
</td>
<td>Signed integer
</td>
<td>16
</td>
<td>-32,768 to 32,767
</td>
<td>0
</td>
</tr>
<tr>
<td><strong>ushort</strong>
</td>
<td>Unsigned integer
</td>
<td>16
</td>
<td>0 to 65,535
</td>
<td>0
</td>
</tr>
<tr>
<td><strong>int</strong>
</td>
<td>Signed integer
</td>
<td>32
</td>
<td>-2,147,483,648 to 2,147,483,647
</td>
<td>0
</td>
</tr>
<tr>
<td><strong>uint</strong>
</td>
<td>Unsigned integer
</td>
<td>32
</td>
<td>0 to 4294967295
</td>
<td>0
</td>
</tr>
<tr>
<td><strong>long</strong>
</td>
<td>Signed integer
</td>
<td>64
</td>
<td>-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807
</td>
<td>0L
</td>
</tr>
<tr>
<td><strong>ulong</strong>
</td>
<td>Unsigned integer
</td>
<td>64
</td>
<td>0 to 18,446,744,073,709,551,615
</td>
<td>0L
</td>
</tr>
<tr>
<td><strong>float</strong>
</td>
<td>Single-precision floating point type
</td>
<td>32
</td>
<td>-3.402823e38 to 3.402823e38
</td>
<td>0.0F
</td>
</tr>
<tr>
<td><strong>double</strong>
</td>
<td>Double-precision floating point type
</td>
<td>64
</td>
<td>-1.79769313486232e308 to 1.79769313486232e308
</td>
<td>0.0D
</td>
</tr>
<tr>
<td><strong>decimal</strong>
</td>
<td>128-bit precise decimal values with 28-29 significant digits
</td>
<td>128
</td>
<td>(+ or -)1.0 x 10e-28 to 7.9 x 10e28
</td>
<td>0.0M
</td>
</tr>
<tr>
<td><strong>char</strong>
</td>
<td>A single Unicode character
</td>
<td>16
</td>
<td>Unicode symbols used in text
</td>
<td>'\0'
</td>
</tr>
<tr>
<td><strong>bool</strong>
</td>
<td>Logical Boolean type
</td>
<td>8
</td>
<td>True or False
</td>
<td>FALSE
</td>
</tr>
<tr>
<td><strong>object</strong>
</td>
<td>Base type of all other types
</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td><strong>string</strong>
</td>
<td>A sequence of characters
</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td><strong>DateTime</strong>
</td>
<td>Represents date and time
</td>
<td>&nbsp;</td>
<td>0:00:00am 1/1/01 to 11:59:59pm 12/31/9999
</td>
<td>&nbsp;</td>
</tr>
</tbody>
</table>
<p><strong>Example:</strong></p>
<pre><code class="csharp">int num;
Console.Write("Min Range: "+ int.MinValue + "Max Range: " + int.MaxValue);
</code></pre>
<div class="output">Min Range: -2147483648Max Range: 2147483647</div>
<p><strong>INITIALIZING VALUE TYPES</strong></p>
<p>Local variables in C# must be initialized before they are used.</p>
<p><code>int myInt;</code></p>
<p><span style="text-decoration: line-through;">You cannot use it before you initialize it.</span> You can initialize it using the following statement:</p>
<p><code>myInt = new int();</code> // Invoke default constructor for int type.&nbsp;</p>
<p>&ndash;or&ndash;</p>
<p><code>myInt = 0;</code> // Assign an initial value, 0 in this example.&nbsp;</p>
<p>You can, of course, have the declaration and the initialization in the same statement as in the following examples:</p>
<p>Using the new operator calls the default constructor of the specific type and assigns the default value to the variable. In the preceding example, the default constructor assigned the value 0 to myInt.</p>
<p><strong>Character escape sequences:</strong></p>
<p>\' &ndash; single quote, needed for character literals</p>
<p>\" &ndash; double quote, needed for string literals</p>
<p>\\ &ndash; backslash</p>
<p>\0 &ndash; Unicode character 0</p>
<p>\a &ndash; Alert (character 7)</p>
<p>\b &ndash; Backspace (character 8)</p>
<p>\f &ndash; Form feed (character 12)</p>
<p>\n &ndash; New line (character 10)</p>
<p>\r &ndash; Carriage return (character 13)</p>
<p>\t &ndash; Horizontal tab (character 9)</p>
<p>\v &ndash; Vertical quote (character 11)</p>
<pre><code class="csharp">string name = "My name: \n \"Ashis \t Kumar\"";
Console.WriteLine(name);

string path = "C:\\Users\\UX\\Downloads\\Video";
//OR Use Verbatim string literals - string path = @"C:\Users\UX\Downloads\Video";
Console.WriteLine(path);

string str = @"My name: ""Ashis""";
//OR - string str = @"My name: "Ashis"";
Console.WriteLine(str);
</code></pre>
<div class="output">
My name:<br/>
 "Ashis          Kumar"<br/>
C:\Users\UX\Downloads\Video<br/>
My name: "Ashis"
</div>
<h2>ARITHMETIC OPERATORS AND SIMPLE CALCULATOR</h2>
<p><strong>Arithmetic Operators:</strong>&nbsp;&nbsp;&nbsp; +&nbsp;&nbsp; -&nbsp;&nbsp; *&nbsp;&nbsp; /&nbsp;&nbsp; %&nbsp;&nbsp; ++&nbsp; --</p>
<p><strong>Relational Operators:</strong>&nbsp;&nbsp;&nbsp; ==&nbsp; !=&nbsp; &gt;&nbsp;&nbsp; &lt;&nbsp;&nbsp; &gt;=&nbsp; &lt;=&nbsp;</p>
<p><strong>Logical Operators:</strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &amp;&amp;&nbsp; ||&nbsp; !</p>
<p><strong>Assignment Operators:</strong>&nbsp;&nbsp;&nbsp; =&nbsp;&nbsp; +=&nbsp; -=&nbsp; *=&nbsp; /=&nbsp; %=&nbsp;</p>
<p><strong>Misc Operators:</strong></p>
<table class="table table-striped table-hover table-condensed table-bordered">
<tbody>
<tr>
<td>
<p>sizeof()</p>
</td>
<td>
<p>Returns the size of a data type.</p>
</td>
<td>
<p>sizeof(int), returns 4.</p>
</td>
</tr>
<tr>
<td>
<p>typeof()</p>
</td>
<td>
<p>Returns the type of a class.</p>
</td>
<td>
<p>typeof(StreamReader);</p>
</td>
</tr>
<tr>
<td>
<p>&amp;</p>
</td>
<td>
<p>Returns the address of an variable.</p>
</td>
<td>
<p>&amp;a; returns actual address of the variable.</p>
</td>
</tr>
<tr>
<td>
<p>*</p>
</td>
<td>
<p>Pointer to a variable.</p>
</td>
<td>
<p>*a; creates pointer named 'a' to a variable.</p>
</td>
</tr>
<tr>
<td>
<p>? :</p>
</td>
<td>
<p>Conditional Expression</p>
</td>
<td>
<p>If Condition is true ? Then value X : Otherwise value Y</p>
</td>
</tr>
<tr>
<td>
<p>is</p>
</td>
<td>
<p>Determines whether an object is of a certain type.</p>
</td>
<td>
<p>If( Ford is Car) // checks if Ford is an object of the Car class.</p>
</td>
</tr>
<tr>
<td>
<p>as</p>
</td>
<td>
<p>Cast without raising an exception if the cast fails.</p>
</td>
<td>
<p>Object obj = new StringReader("Hello");</p>
<p>StringReader r = obj as StringReader;</p>
</td>
</tr>
</tbody>
</table>
<pre><code class="csharp">int num1, num2;
int add, sub, mul, rem;
float div;

Console.Write("Enter 1st Number:\t");
num1 = Convert.ToInt32(Console.ReadLine());

Console.Write("Enter 2nd Number:\t");
num2 = Convert.ToInt32(Console.ReadLine());

add = num1 + num2;
sub = num1 - num2;
mul = num1 * num2;
div = (float)num1 / num2;
rem = num1 % num2;

Console.WriteLine("Addition:\t{0}", add);
Console.WriteLine("Subtraction:\t{0}", sub);
Console.WriteLine("Multiplication:\t{0}", mul);
Console.WriteLine("Division:\t{0}", div);
Console.WriteLine("Remainder:\t{0}", rem);
</code></pre>
<div class="output">
Enter 1st Number:       13<br/>
Enter 2nd Number:       5<br/>
Addition:       18<br/>
Subtraction:   8<br/>
Multiplication: 65<br/>
Division:       2.6<br/>
Remainder:      3
</div>
<h2>ARRAY</h2>
<pre><code class="csharp">int[] myIntArr = new int[2];
myIntArr[0] = 34;
myIntArr[1] = 12;
Console.WriteLine(myIntArr[1]);

string[] myStrArr = new string[2];
myStrArr[0] = "24";
myStrArr[1] = "Ashis";
Console.WriteLine(myStrArr[1]);

foreach(string x in myStrArr)
{
Console.WriteLine("Ex: " + x);
}
</code></pre>
<div class="output">
12<br/>
Ashis<br/>
Ex: 24<br/>
Ex: Ashis
</div>
<h2>METHODS</h2>
<pre><code class="csharp">class ExampleOne
{
    public static void Main()
    {
        int n1 = 12, n2 = 5;
        ExampleOne obj = new ExampleOne();
        Console.WriteLine("Sum: " + obj.sum(n1, n2));
        Console.ReadKey();
    }
    public int sum(int num1, int num2)
    {
        return num1 + num2;
    }
}
</code></pre>
<div class="output">Sum: 17</div>
<pre><code class="csharp">class ExampleOne
{
    public static void Main()
    {
        ExampleOne.sum(20,30);
        Console.ReadKey();
    }
    public static void sum(int num1, int num2)
    {
        Console.WriteLine("Sum: " + (num1 + num2));
    }
}
</code></pre>
<div class="output">Sum: 50</div>
<p><b>Program (Static Example):</b></p>
<pre><code class="csharp">class ExampleOne
{
    public static void Main()
    {
        int n1 = 50;
        int n2 = 20;
        Console.WriteLine(ExampleOne.sum(n1, n2));
        Console.ReadKey();
    }
    public static int sum(int num1, int num2)
    {
        num1 = 10; num2 = 20;
        return num1 + num2;
    }
}
</code></pre>
<div class="output">Sum: 30</div>
<table class="table table-condensed table-bordered">
    <tr>
        <th>Pass By Value</th>
        <th>Pass By Reference</th>
    </tr>
    <tr>
        
        <td>
            <pre><code class="csharp">class ExampleOne
{
    public static void Main()
    {
        int n1 = 50;
        myFunc(n1);
        Console.WriteLine(n1);
        Console.ReadKey();
    }
    public static void myFunc(int num1)
    {
        num1 = 10;
    }
}
</code></pre>
        </td>
        <td>
            <pre><code class="csharp">class ExampleOne
{
    public static void Main()
    {
        int n1 = 50;
        myFunc(ref n1);
        Console.WriteLine(n1);
        Console.ReadKey();
    }
    public static void myFunc(ref int num1)
    {
        num1 = 10;
    }
}
</code></pre>
        </td>
    </tr>
    <tr>
        <td>Output: 50</td>
        <td>Output: 10</td>
    </tr>
</table>
<p><b>Program: (Use of out for multiple return values)</b></p>
<pre><code class="csharp">class ExampleOne
{
    public static void Main()
    {
        int n1 = 50, n2 = 10, sum = 0, mul = 0;
        myFunc(n1, n2, out sum, out mul);
        Console.WriteLine("Sum: {0} and Multiplication: {1}",sum,mul);
        Console.ReadKey();
    }
    public static void myFunc(int num1, int num2, out int sum, out int mul)
    {
        sum = num1 + num2;
        mul = num1 * num2;
    }
}
</code></pre>
<div class="output">Sum: 60 and Multiplication: 500</div>
<p><b>Program: (Use of params)</b></p>
<pre><code class="csharp">class ExampleOne
{
    public static void Main()
    {
        string[] nameArr = new string[4];
        nameArr[0] = "Ashis";
            nameArr[1] = "Kumar";
            nameArr[2] = "Alok";
            nameArr[3] = "Ranjan";
            // We can't write myFunc(); without passing the array But using "params" it is possible
            myFunc(nameArr);
            myFunc("Hi", "Hello");
            Console.ReadKey();
    }
    public static void myFunc(params string[] strArr)
    {
        foreach(string str in strArr)
        {
            Console.WriteLine(str);
        }
        Console.WriteLine("Array Length: {0}", strArr.Length);
    }
}
</code></pre>
<div class="output">
Ashis<br/>
Kumar<br/>
Alok<br/>
Ranjan<br/>
Array Length: 4<br/>
Hi<br/>
Hello<br/>
Array Length: 2
</div>
<p><b>Conditions and uses of params:</b></p>
<ol>
    <li>Able to pass array elements in the method parameter</li>
    <li>In the method we can only use 1 params.</li>
    <li><code>public static void myFunc(int x, params string[] strArr) </code>is possible. Because params can only use at last.</li>
</ol>
<h2>METHOD OVERLOADING</h2>
<pre><code class="csharp">class ExampleOne
{
    public static void Main()
    {
        Console.WriteLine("Sum of two int: {0}", sum(20, 30));
        Console.WriteLine("Sum of two double: {0}", sum(20.50, 30));
        Console.WriteLine("Sum of two strings: {0}", sum("Ashis ", "Kumar"));
        Console.ReadKey();
    }
    public static int sum(int n1, int n2)
    {
        int add = n1 + n2;
        return add;
    }
    public static double sum(double n1, double n2)
    {
        double add = n1 + n2;
        return add;
    }
    public static string sum(string n1, string n2)
    {
        string add = n1 + n2;
        return add;
    }
}
</code></pre>
<div class="output">
Sum of two int: 50<br/>
Sum of two double: 50.5<br/>
Sum of two strings: Ashis Kumar
</div>
<h2>CLASSES AND OBJECTS</h2>
<table class="table table-condensed table-bordered">
    <tr>
        <td><pre><code class="csharp">class Box
{
    public double l, b, h;
    public double volume(double l,double b, double h)
    {
        return (l * b * h);
    }
}
class ExampleOne
{   
    public static void Main()
    {
        Box box1 = new Box();
        box1.l = 20;
        box1.b = 10;
        box1.h = 5;
        Console.WriteLine("Volume of Box1: {0}", box1.volume(box1.l, box1.b, box1.h));
        Box box2 = new Box();
        box2.l = 4;
        box2.b = 5;
        box2.h = 2;
        Console.WriteLine("Volume of Box2: {0}", box2.volume(box2.l, box2.b, box2.h));
        Console.ReadKey();
    }
}
</code></pre></td>
        <td><pre><code class="csharp">class Box
{
    public double l, b, h;
    public double volume()
    {
        return (this.l * this.b * this.h);
    }
}
class ExampleOne
{   
    public static void Main()
    {
        Box box1 = new Box();
        box1.l = 20;
        box1.b = 10;
        box1.h = 5;
        Console.WriteLine("Volume of Box1: {0}", box1.volume());
        Box box2 = new Box();
        box2.l = 4;
        box2.b = 5;
        box2.h = 2;
        Console.WriteLine("Volume of Box2: {0}", box2.volume());
        Console.ReadKey();
    }
}
</code></pre></td>
    </tr>
    <tr>
        <td><div class="output">Volume of Box1: 1000<br/>Volume of Box2: 40</div></td>
        <td><div class="output">Volume of Box1: 1000<br/>Volume of Box2: 40</div></td>
    </tr>
</table>
<h2>CONSTRUCTOR AND DESTRUCTOR</h2>
<ul style="list-style-type: square;">
<li>They are called automatically even we don&rsquo;t define them by ourselves</li>
<li>Must have same name as class name</li>
<li>Initialized automatically when an instance or object is created</li>
<li>It doesn&rsquo;t return any values</li>
<li>We can pass parameters</li>
<li>Mostly used to initialize the variables or values</li>
<li>Destructor is called when it reaches at out of scope of instance</li>
</ul>
<table class="table table-condensed table-bordered">
    <tr>
        <th>Example: 1</th>
        <th>Example: 2</th>
    </tr>
    <tr>
        <td><pre><code class="csharp">class Box
{
    public Box()
    {
        Console.WriteLine("Constructor has initialized");
    }
    ~Box(){
        Console.WriteLine("Destructor has called");
    }
}
class ExampleOne
{   
    public static void Main()
    {
        Box box1 = new Box();
    }
}
</code></pre></td>
        <td><pre><code class="csharp">class Box
{
    public double l, b, h;
    public double volume()
    {
        return (this.l * this.b * this.h);
    }
    public Box(double le, double br, double hi)
    {
        this.l = le;
        this.b = br;
        this.h = hi;
    }
}
class ExampleOne
{   
    public static void Main()
    {
        Box box1 = new Box(10,20,30);
        Console.WriteLine("Volume of Box1: {0}", box1.volume());
        Console.ReadKey();
    }
}
</code></pre></td>
    </tr>
    <tr>
        <td><div class="output">Constructor has initialized<br/>Destructor has called</div></td>
        <td><div class="output">Volume of Box1: 6000 </div></td>
    </tr>
</table>
<h2>CLASS INHERITANCE</h2>
<img src="" alt="">
<p>We can’t inherit 2 base classes at the same time (Only one is allowed) but we can indirectly inherit to the base class. Just like</p>
<table class="table table-bordered table-condensed">
    <tr>
        <td><pre><code class="csharp">class Polygon{}
class Cls1 : Polygon {}
class Cls2 : Polygon, Cls1 {}
</code></pre></td>
        <td><pre><code class="csharp">class Polygon{}
class Cls1 : Polygon {}
class Cls2 : Cls1 {}
</code></pre></td>
    </tr>
    <tr>
        <td><p style="color: red;">Wrong</p></td>
        <td><p>In this way Cls2 can access the class Polygon</p></td>
    </tr>
</table>
<p>When we create an instance of child class then it automatically creates the instance of the base class.</p>
<pre><code class="csharp">class Polygon
{
    public double height, width;
    public void setValues(double h, double w)
    {
        this.height = h;
        this.width = w;
    }
}
class Rectangle : Polygon
{
    public double area()
    {
        return this.height * this.width;
    }
}
class Triangle : Polygon
{
    public double area()
    {
        return this.height * this.width /2;
    }
}
class ExampleOne
{
    public static void Main()
    {
        Rectangle rect = new Rectangle();
        Triangle tri = new Triangle();
        rect.setValues(20, 30);
        tri.setValues(20, 30);
        Console.WriteLine("Area of Rectangle: {0}", rect.area());
        Console.WriteLine("Area of Triangle: {0}", tri.area());
        Console.ReadKey();
    }
}
</code></pre>
<div class="output">Area of Rectangle: 600<br/>Area of Triangle: 300</div>
<h2>METHOD HIDING</h2>
<table class="table table-bordered table-condensed">
    <tr>
        <th>Method: 1</th>
        <th>Method: 2</th>
        <th>Method: 3</th>
    </tr>
    <tr>
        <td><pre><code class="csharp">class Fc
{
    public void display()
    {
        Console.WriteLine("This is Fc Class");
    }
}
class Sc : Fc
{
    public new void display()
    {
        Console.WriteLine("This is Sc Class");
    }
}
class ExampleOne
{
    public static void Main()
    {
        Sc obj = new Sc();
        obj.display();
        Console.ReadKey();
    }
}
</code></pre></td>
        <td><pre><code class="csharp">class Fc
{
    public void display()
    {
        Console.WriteLine("This is Fc Class");
    }
}
class Sc : Fc
{
    public new void display()
    {
        Console.WriteLine("This is Sc Class");
    }
}
class ExampleOne
{
    public static void Main()
    {
        Sc obj = new Sc();
        ((Fc)obj).display();
        Console.ReadKey();
    }
}
</code></pre></td>
        <td><pre><code class="csharp">class Fc
{
    public void display()
    {
        Console.WriteLine("This is Fc Class");
    }
}
class Sc : Fc
{
    public new void display()
    {
        Console.WriteLine("This is Sc Class");
    }
}
class ExampleOne
{
    public static void Main()
    {
        Fc obj = new Sc();
        obj.display();
        Console.ReadKey();
    }
}
</code></pre></td>
    </tr>
    <tr>
        <td><div class="output"><b>Note:</b> Without using ‘new’ it will show the output but with a warning for method hiding.</div></td>
        <td><div class="output"><b>Note:</b> Without using ‘new’ it will show the output but with a warning for method hiding.</div></td>
        <td><div class="output"><b>Note:</b> Without using ‘new’ it will show the output but with a warning for method hiding.</div></td>
    </tr>
    <tr>
        <td><div class="output">This is Fc Class</div></td>
        <td><div class="output">This is Fc Class</div></td>
        <td><div class="output">This is Fc Class</div></td>
    </tr>
</table>
<h2>POLYMORPHISM</h2>
<pre><code class="csharp">public class Drawing
{
    public virtual void Draw()
    {
        Console.WriteLine("This is just a generic drawing object");
    }
}
class Circle : Drawing
{
    public override void Draw()
    {
        Console.WriteLine("This is a Circle");
    }
}
class Square : Drawing
{
    public override void Draw()
    {
        Console.WriteLine("This is a Square");
    }
}
class Line : Drawing
{
    public override void Draw()
    {
        Console.WriteLine("This is a Line");
    }
}

class ExampleOne
{
    public static void Main()
    {
        Drawing[] obj = new Drawing[4];
        obj[0] = new Circle();
        obj[1] = new Line();
        obj[2] = new Square();
        obj[3] = new Drawing();

        foreach(Drawing draw in obj)
        {
            draw.Draw();
        }
        Console.ReadKey();
    }
}
</code></pre>
<div class="output">
This is a Circle<br/>
This is a Line<br/>
This is a Square<br/>
This is just a generic drawing object
</div>
<h2>DIFFERENCE BETWEEN METHOD OVERRIDING AND METHOD HIDING</h2>
<table class="table table-bordered table-condensed">
    <tr>
        <th>METHOD OVERRIDING</th>
        <th>METHOD HIDING</th>
    </tr>
    <tr>
        <td><pre><code class="csharp">public class Drawing
{
    public virtual void Draw()
    {
        Console.WriteLine("This is just a generic drawing object");
    }
}
class Circle : Drawing
{
    public override void Draw()
    {
        Console.WriteLine("This is a Circle");
    }
}

class ExampleOne
{
    public static void Main()
    {
        Drawing obj = new Circle();
        obj.Draw();
        Console.ReadKey();
    }
}
</code></pre></td>
        <td><pre><code class="csharp">public class Drawing
{
    public void Draw()
    {
        Console.WriteLine("This is just a generic drawing object");
    }
}
class Circle : Drawing
{
    public new void Draw()
    {
        Console.WriteLine("This is a Circle");
    }
}

class ExampleOne
{
    public static void Main()
    {
        Drawing obj = new Circle();
        obj.Draw();
        Console.ReadKey();
    }
}
</code></pre></td>
    </tr>
    <tr>
        <td><div class="output">This is a Circle</div></td>
        <td><div class="output">This is just a generic drawing object</div></td>
    </tr>
</table>
<h2>GETTER AND SETTER</h2>
<pre><code class="csharp">public class Book
{
    private int _bookId;
    private string _bookName;
    private int _noOfPages = 250;

    public void SetBookId(int id)
    {
        if(id < 0)
            //Console.WriteLine("Book ID can't be a negative value");
            throw new Exception("Book ID can't be a negative value");
        this._bookId = id;
    }
    public int GetBookId()
    {
        return this._bookId;
    }
    public void SetBookName(string bookname)
    {
        if (string.IsNullOrEmpty(bookname))
            Console.WriteLine("Book name can't be empty");
        this._bookName = bookname;
    }
    public string GetBookName()
    {
        return this._bookName;
    }
    public int GetNoOfPages()
    {
        return this._noOfPages;
    }
}

class ExampleOne
{
    public static void Main()
    {
        Book obj = new Book();
        obj.SetBookId(10);
        obj.SetBookName("C#");
        Console.WriteLine("Book ID: {0}", obj.GetBookId());
        Console.WriteLine("Book Name: {0}", obj.GetBookName());
        Console.WriteLine("Book Name: {0}", obj.GetNoOfPages());
        Console.ReadKey();
    }
}
</code></pre>
<div class="output">Book ID: 10<br/>Book Name: C#<br/>Book Name: 250</div>
<h2>PROPERTIES IN C#</h2>
<pre><code class="csharp">public class Book
{
    private int _bookId;
    private string _bookName;
    private int _noOfPages = 250;
        
    public int bookid
    {
        set
        {
            if (value < 0)
                //Console.WriteLine("Book ID can't be a negative value");
                throw new Exception("Book ID can't be a negative value");
            this._bookId = value;
        }
        get
        {
            return this._bookId;
        }
    }
    public string bookname
    {
        set
        {
            if (string.IsNullOrEmpty(value))
                Console.WriteLine("Book name can't be empty");
            this._bookName = value;
        }
        get
        {
            return this._bookName;
        }
    }
    public int noofpages
    {
        get
        {
            return this._noOfPages;
        }
    }
}

class ExampleOne
{
    public static void Main()
    {
        Book obj = new Book();
        obj.bookid = 10;
        obj.bookname = "The C# Book";
        Console.WriteLine("Book ID: {0}", obj.bookid);
        Console.WriteLine("Book Name: {0}", obj.bookname);
        Console.WriteLine("Book Name: {0}", obj.noofpages);
        Console.ReadKey();
    }
}
</code></pre>
<div class="output">Book ID: 10<br/>Book Name: The C# Book<br/>Book Name: 250</div>

<table class="table table-bordered table-condensed">
    <tr>
        <th>Program: 1</th>
        <th>Program: 2</th>
        <th>Program: 3</th>
    </tr>
    <tr>
        <td><pre><code class="csharp">public class Book
{
    private string _author;

    public string author
    {
        set
        {
            this._author = value;
        }
        get
        {
            return this._author;
        }
    }
}

class ExampleOne
{
    public static void Main()
    {
        Book obj = new Book();
        obj.author = "Ashis Kumar";
        Console.WriteLine("Book Author: {0}", obj.author);
        Console.ReadKey();
    }
}
</code></pre></td>
        <td><pre><code class="csharp">public class Book
{
    private string _author;

    public void SetAuthor(string author)
    {
        this._author = author;
    }
    public string GetAuthor()
    {
        return this._author;
    }
}

class ExampleOne
{
    public static void Main()
    {
        Book obj = new Book();
        obj.SetAuthor("Ashis Kumar");
        Console.WriteLine("Book Author: {0}", obj.GetAuthor());
        Console.ReadKey();
    }
}
</code></pre></td>
        <td><pre><code class="csharp">public class Book
{
    public string Author { set; get; }
}

class ExampleOne
{
    public static void Main()
    {
        Book obj = new Book();
        obj.Author = "Ashis Kumar";
        Console.WriteLine("Book Author: {0}", obj.Author);
        Console.ReadKey();
    }
}
</code></pre></td>
    </tr>
    <tr>
        <td><div class="output">Book Author: Ashis Kumar</div></td>
        <td><div class="output">Book Author: Ashis Kumar</div></td>
        <td><div class="output">Book Author: Ashis Kumar</div></td>
    </tr>
</table>
<h2>INTERFACES</h2>
<ul style="list-style-type: circle;">
<li>An interface is like an abstract base class <strong>with only abstract members</strong>. Any class or struct that implements the interface must <strong>implement all its members</strong>.</li>
<li>An interface <strong>can't be instantiated directly</strong>. Its members are <strong>implemented by any class</strong> or struct that implements the interface.</li>
<li>Interfaces can contain events, indexers, methods, and properties.</li>
<li>Interfaces contain <strong>no implementation of methods</strong>. Means Interfaces can&rsquo;t contain fields. Interface methods can&rsquo;t have a definition.</li>
<li>By default interface members are public. So don&rsquo;t add public in interface methods. But we must add public when we implement the interface within a class.</li>
<li>A <strong>class or struct can implement multiple interfaces</strong>. A <strong>class can inherit a base class</strong> and also <strong>implement one or more interfaces</strong>.</li>
</ul>
<pre><code class="csharp">interface IText1
{
    // We can't initialize a member method with access modifiers. 
    // By default, interface members are public.
    // Interface member cannot have definition.
    // Interface just contain the prototypes of method.
    void print1();
}
interface IText2
{
    void print2();
}
// Class can inherit multiple interfaces at a time.
// We can't inherit multiple base classes at a time.
class Text : IText1, IText2
{
    // Must add public to access the interface member
    public void print1()
    {
        Console.WriteLine("Hello World!  - 1");
    }
    public void print2()
    {
        Console.WriteLine("Hello World!  - 2");
    }
}
class ExampleOne
{
    public static void Main()
    {
        Text obj = new Text();
        obj.print1();
        obj.print2();
        Console.ReadKey();
    }
}
</code></pre>
<p style="text-align: center;"><b>OR</b></p>
<pre><code class="csharp">interface IText1
{
    void print1();
}
interface IText2
{
    void print2();
}
class Text : IText1, IText2
{
    public void print1()
    {
        Console.WriteLine("Hello World!  - 1");
    }
    public void print2()
    {
        Console.WriteLine("Hello World!  - 2");
    }
}
class ExampleOne
{
    public static void Main()
    {
        IText1 obj1 = new Text();
        obj1.print1();
        IText2 obj2 = new Text();
        obj2.print2();
        Console.ReadKey();
    }
}
</code></pre>
<div class="output">Hello World!  - 1<br/>Hello World!  - 2</div>
<h2>ABSTRACT CLASSES</h2>
<p>Sometimes we only make classes that represents base classes and we don’t want anyone to create objects of these classes. So, we need to make these classes using “abstract”. Abstract class means no object of this class can be instantiated or created. But they can be used as base classes. So, we can derive from these classes, but they can’t use as normal classes. </p>
<pre><code class="csharp">// abstract class can't be 'sealed' class
// 'sealed' class means the class can't be use as a base class
// 'sealed' class example: public sealed class PrintText{ }
// class can't use 'abstract' and 'sealed' at a time
public abstract class PrintText
{
    // We can't provide defination to an abstract method
    // It is not neccessary that an abstract class contain an abstract method
    // abstract memebrs can't be "private"
    // abstract method can't be marked as "virtual / static" keyword
    public abstract void print1();
    // Abstract class can contain normal methods
    public void print2()
    {
        Console.WriteLine("Print 2");
    }
}
class ExampleOne : PrintText
{
    public override void print1()
    {
        Console.WriteLine("Print 1");
    }
    public static void Main()
    {
        ExampleOne obj = new ExampleOne();
        obj.print1();
        obj.print2();
        Console.ReadKey();
    }
}
</code></pre>
<div class="output">Print 1<br/>Print 2</div>
<h2>ABSTRACT CLASS VERSUS INTERFACE</h2>
<table class="table table-bordered table-condensed table-striped table-hover">
    <tr class="info">
        <th>Interface</th>
        <th>Abstract Class</th>
    </tr>
    <tr>
        <td>Interface support multiple inheritance</td>
        <td>Abstract Class doesn't support multiple inheritance</td>
    </tr>
    <tr>
        <td>Interface doesn't contains Data Member</td>
        <td>Abstract Class contains Data Member</td>
    </tr>
    <tr>
        <td>Interface doesn't contains Constructors</td>
        <td>Abstract Class contains Constructors</td>
    </tr>
    <tr>
        <td>An Interface contains only incomplete member (signature of member)</td>
        <td>An Abstract Class contains both incomplete (abstract) and complete member</td>
    </tr>
    <tr>
        <td>An Interface can't have access modifiers by default everything is assumed as public</td>
        <td>An Abstract Class can contain access modifiers for the subs, functions, properties</td>
    </tr>
    <tr>
        <td>Member of Interface can not be static</td>
        <td>Only complete Member of Abstract Class can be static</td>
    </tr>
</table>
<h2>DELEGATES</h2>
<p>Delegate is a type which holds the method(s) reference in an object.</p>
<p>It is also referred to as a type safe function pointer.</p>
<p>Generally delegate is used for multiple use of methods.</p>
<pre><code class="csharp">public delegate int addNosDelegate(int num1, int num2);
class ExampleOne
{
    // Object reference is not required for static methods
    public static int addNos(int n1, int n2) {
        return n1 + n2;
    }
    public static void Main()
    {
        addNosDelegate obj = new addNosDelegate(addNos);
        int result = obj(50, 40);
        Console.WriteLine(result);
        Console.ReadKey();
    }
}
</code></pre>
<div class="output">90</div>
<pre><code class="csharp">class ExampleOne
{
    public static int addNos(int n1, int n2)
    {
        return n1 + n2;
    }
    public static int subNos(int n1, int n2)
    {
        return n1 - n2;
    }
    public static int multNos(int n1, int n2)
    {
        return n1 * n2;
    }
    public static void Main()
    {
        int num1 = 10;
        int num2 = 5;
        oprationDelegate obj1 = new oprationDelegate(addNos);
        Console.WriteLine("Addition: " + obj1(num1, num2));

        oprationDelegate obj2 = new oprationDelegate(subNos);
        Console.WriteLine("Substraction: " + obj2(num1, num2));

        oprationDelegate obj3 = new oprationDelegate(multNos);
        Console.WriteLine("Multiplication: " + obj3(num1, num2));
        Console.ReadKey();
    }
}
</code></pre>
<div class="output">Addition: 15<br/>Substraction: 5<br/>Multiplication: 50</div>












        </div>
    </div>
    <div class="footer">
        <div class="container">
            <a href="https://www.mrashis.com" title="mrashis.com" target="_blank">mrashis.com</a>
        </div>
    </div>

</body>
</html>
