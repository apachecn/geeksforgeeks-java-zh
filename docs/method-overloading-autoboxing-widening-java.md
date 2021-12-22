# Java 中带自动装箱和加宽的方法重载

> 原文:[https://www . geesforgeks . org/method-重载-自动装箱-加宽-java/](https://www.geeksforgeeks.org/method-overloading-autoboxing-widening-java/)

前提条件:[方法重载](https://www.geeksforgeeks.org/different-ways-method-overloading-java/)、[自动装箱拆箱](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)

在 Java 中有两种类型的变量:原语类型和引用类型。将原语类型转换为相应的包装对象称为自动装箱，将包装对象转换为相应的原语类型称为取消装箱。

**自动装箱超载方法**

在方法重载中，您可能会遇到签名将引用类型或基元类型作为形式参数的情况。编译器首先搜索具有相同数据类型的参数的方法。如果您使用包装类对象作为实际参数，并且编译器没有找到具有相同引用类型(即类或接口类型)的参数的方法，那么它将开始搜索具有相应原始数据类型的参数的方法。

```
// Java program to illustrate 
// Autoboxing
// while resolving data type as:
// a)reference b)primitive 
import java.io.*;

public class Conversion 
{

    // 1.overloaded method with primitive formal argument
    public void method(int i)
    {

        System.out.println("Primitive type int formal argument :" + i);
    }

    // overloaded method with reference formal argument
    public void method(Integer i)
    {

        System.out.println("Reference type Integer formal argument :" + i);
    }

    // 2\. overloaded method primitive formal argument
    // and to be invoked for wrapper Object as overloaded method
    // with wrapper object of same(Long) type as an argument is not 
    // available.
    public void method(long i)
    {

        System.out.println("Primitive type long formal argument :" + i);
    }
}

class GFG 
{

    public static void main (String[] args) 
    {
        Conversion c = new Conversion();

        // invoking the method with different signature.
        c.method(10);
        c.method(new Integer(15));
        c.method(new Long(100));

        // Using short will give, argument mismatch;
        // possible lossy conversion from int to short
        // c.method(new Short(15));

    }
}
```

输出:

```
Primitive type int formal argument :10
Reference type Integer formal argument :15
Primitive type long formal argument :100

```

**加宽超载法**

如果编译器找不到任何与自动装箱相对应的方法，它将开始搜索扩展的基本数据类型的方法参数。
在下面的示例中，我们正在调用带有原语( **int** )形式实参的重载方法，该实参的数据类型与实际实参的数据类型相同。我们正在调用另一个带有长包装对象参数的方法。编译器开始搜索具有相同引用类型的方法(长包装类)。由于没有带**长包装类**参数的方法。因此，它寻找能够接受大于长基元数据类型的参数作为参数的方法。在这种情况下，它找到一个带有**浮点原始数据类型**的方法并调用它。

```
// Java program to illustrate method 
// overloading 
// in case of widening
import java.io.*;

public class Conversion 
{
    // overloaded method
    public void method(int i)
    {
        System.out.println("Primitive type int formal argument :" + i);
    }

    // overloaded method primitive formal argument
    // and to be invoked for wrapper Object as 

    public void method(float i)
    {

        System.out.println("Primitive type float formal argument :" + i);
    }
}

class GFG 
{

    public static void main (String[] args)
    {

        Conversion c = new Conversion();

        // invoking the method with signature
        // has widened data type
        c.method(10);
        c.method(new Long(100));
    }
}
```

输出:

```
Primitive type int formal argument :10
Primitive type float formal argument :100.0
```

**加宽加装箱重载方法**

如果加宽和拳击同时发生会怎么样？编译器能做什么方法调用？
基元类型的扩展优先于装箱和 var-args。但是扩展和原始类型的装箱不能一起工作。

```
// Java program  to illustrate method 
// overloading for widening
// and autoboxing together
import java.io.*;

public class Conversion 
{
    // overloaded method with reference type formal argument
    public void method(Integer a)
    {

        System.out.println("Primitive type byte formal argument :" + a);
    }

}

class GFG 
{

    public static void main (String[] args) 
    {

        Conversion c = new Conversion();

        // invoking the method 
        byte val = 5;
        c.method(val);
    }
}
```

输出:

```
25: error: incompatible types: byte cannot be converted to Integer
        c.method(val);
                 ^
 Some messages have been simplified; recompile with -Xdiags:verbose to get full output
1 error

```

但是**装箱后加宽是可以接受的**如果这被传递给类型为 Object 的引用。请参见下面的示例。

```
// Java program to illustrate
// autoboxing followed by 
// widening in reference type
// variables
import java.io.*;

public class Conversion 
{

    // overloaded method with reference type
    // formal argument
    public void method(Object b)
    {

        // Object b is typecasted to Byte and then printed 
        Byte bt = (Byte) b;
        System.out.println("reference type formal argument :" + bt);
    }

}

class GFG 
{

    public static void main (String[] args) 
    {

        Conversion c = new Conversion();

        byte val = 5;

        // b is first widened to Byte 
        // and then Byte is passed to Object. 
        c.method(val);
    }
}
```

输出:

```
Primitive type byte formal argument :5

```

**方法重载 [Var-args](https://www.geeksforgeeks.org/method-overloading-ambiguity-varargs-java/) 参数**

基元类型的扩展比 var-args 具有更高的优先级。
**例:**

```
// Java program to illustrate
// method overloading for var-args
// and widening concept together
import java.io.*;

public class Conversion
{
    // overloaded method primitive(byte) var-args formal argument
    public void method(byte... a)
    {
        System.out.println("Primitive type byte formal argument :" + a);
    }

    // overloaded method primitive(int) formal arguments
    public void method(long a, long b)
    {
        System.out.println("Widening type long formal argument :" + a);
    }
}

class GFG 
{

    public static void main (String[] args)
    {
        Conversion c = new Conversion();

        // invokes the method having widening 
        // primitive type parameters.
        byte val = 5;
        c.method(val,val);
    }
}
```

输出:

```
Widening type long formal argument :5

```

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。