# Java 中的泛型

> 原文:[https://www.geeksforgeeks.org/generics-in-java/](https://www.geeksforgeeks.org/generics-in-java/)

**泛型**是指**参数化类型**。其思想是允许类型(整数、字符串、…等和用户定义的类型)成为方法、类和接口的参数。使用泛型，可以创建使用不同数据类型的类。
对参数化类型进行操作的实体，如类、接口或方法，称为泛型实体。

**为什么是仿制药？**

**对象**是所有其他类的超类，对象引用可以引用任何类型的对象。这些功能缺乏类型安全性。泛型增加了类型安全特性。我们将在后面的例子中讨论这种类型的安全特性。
Java 中的泛型类似于 C++中的[模板](http://geeksquiz.com/templates-cpp/)。例如，像 HashSet、ArrayList、HashMap 等类很好地使用了泛型。这两种泛型类型的方法有一些根本的区别。

**泛型类**
和 C++一样，我们在泛型类创建中使用< >来指定参数类型。要创建泛型类的对象，我们使用以下语法。

```java
// To create an instance of generic class 
BaseType <Type> obj = new BaseType <Type>()

Note: In Parameter type we can not use primitives like 
      'int','char' or 'double'.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Simple Java program to show working of user defined
// Generic classes

// We use < > to specify Parameter type
class Test<T>
{
    // An object of type T is declared
    T obj;
    Test(T obj) {  this.obj = obj;  }  // constructor
    public T getObject()  { return this.obj; }
}

// Driver class to test above
class Main
{
    public static void main (String[] args)
    {
        // instance of Integer type
        Test <Integer> iObj = new Test<Integer>(15);
        System.out.println(iObj.getObject());

        // instance of String type
        Test <String> sObj =
                          new Test<String>("GeeksForGeeks");
        System.out.println(sObj.getObject());
    }
}
```

输出:

```java
15
GeeksForGeeks
```

我们也可以在泛型类中传递多个类型参数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Simple Java program to show multiple
// type parameters in Java Generics

// We use < > to specify Parameter type
class Test<T, U>
{
    T obj1;  // An object of type T
    U obj2;  // An object of type U

    // constructor
    Test(T obj1, U obj2)
    {
        this.obj1 = obj1;
        this.obj2 = obj2;
    }

    // To print objects of T and U
    public void print()
    {
        System.out.println(obj1);
        System.out.println(obj2);
    }
}

// Driver class to test above
class Main
{
    public static void main (String[] args)
    {
        Test <String, Integer> obj =
            new Test<String, Integer>("GfG", 15);

        obj.print();
    }
}
```

输出:

```java
GfG
15
```

**泛型函数:**
我们还可以根据传递给泛型方法的参数类型，编写可以用不同类型的参数调用的泛型函数，编译器处理每个方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Simple Java program to show working of user defined
// Generic functions

class Test
{
    // A Generic method example
    static <T> void genericDisplay (T element)
    {
        System.out.println(element.getClass().getName() +
                           " = " + element);
    }

    // Driver method
    public static void main(String[] args)
    {
         // Calling generic method with Integer argument
        genericDisplay(11);

        // Calling generic method with String argument
        genericDisplay("GeeksForGeeks");

        // Calling generic method with double argument
        genericDisplay(1.0);
    }
}
```

输出:

```java
java.lang.Integer = 11
java.lang.String = GeeksForGeeks
java.lang.Double = 1.0
```

**泛型仅适用于引用类型:**
当我们声明泛型类型的实例时，传递给类型参数的类型参数必须是引用类型。我们不能使用像 **int** 、 **char 这样的原始数据类型。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
Test<int> obj = new Test<int>(20); 
```

上面这一行导致编译时错误，可以通过使用类型包装器封装基元类型来解决。

但是基元类型数组可以通过传递给类型参数，因为数组是引用类型。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
ArrayList<int[]> a = new ArrayList<>();
```

**泛型类型根据其类型参数而不同:**

考虑下面的 Java 代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Simple Java program to show working
// of user-defined Generic classes

// We use < > to specify Parameter type
class Test<T>
{
    // An object of type T is declared
    T obj;
    Test(T obj) {  this.obj = obj;  }  // constructor
    public T getObject()  { return this.obj; }
}

// Driver class to test above
class Main
{
    public static void main (String[] args)
    {
        // instance of Integer type
        Test <Integer> iObj = new Test<Integer>(15);  
        System.out.println(iObj.getObject());

        // instance of String type
        Test <String> sObj =
                          new Test<String>("GeeksForGeeks");
        System.out.println(sObj.getObject());
        iObj = sObj; //This results an error  
    }
}
```

**输出:**

```java

error:
 incompatible types:
 Test cannot be converted to Test 
```

尽管 iObj 和 sObj 属于 Test 类型，但它们是对不同类型的引用，因为它们的类型参数不同。泛型通过这一点增加了类型安全性并防止了错误。
**泛型的优势:**
使用泛型的程序比非泛型代码有很多好处。

**1。代码重用:**我们可以一次性编写一个方法/类/接口，并将其用于我们想要的任何类型。

**2。类型安全:**泛型使错误在编译时出现，而不是在运行时出现(最好在编译时知道代码中的问题，而不是在运行时使代码失败)。假设您想创建一个存储学生姓名数组列表，如果程序员错误地添加了一个整数对象而不是字符串，编译器会允许。但是，当我们从数组列表中检索这些数据时，它会在运行时导致问题。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Simple Java program to demonstrate that NOT using
// generics can cause run time exceptions
import java.util.*;

class Test
{
    public static void main(String[] args)
    {
        // Creatinga an ArrayList without any type specified
        ArrayList al = new ArrayList();

        al.add("Sachin");
        al.add("Rahul");
        al.add(10); // Compiler allows this

        String s1 = (String)al.get(0);
        String s2 = (String)al.get(1);

        // Causes Runtime Exception
        String s3 = (String)al.get(2);
    }
}
```

输出:

```java
Exception in thread "main" java.lang.ClassCastException: 
   java.lang.Integer cannot be cast to java.lang.String
    at Test.main(Test.java:19)
```

**仿制药如何解决这个问题？**
在定义 ArrayList 的时候，我们可以指定这个列表只能取 String 对象。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Using generics converts run time exceptions into 
// compile time exception.
import java.util.*;

class Test
{
    public static void main(String[] args)
    {
        // Creating a an ArrayList with String specified
        ArrayList <String> al = new ArrayList<String> ();

        al.add("Sachin");
        al.add("Rahul");

        // Now Compiler doesn't allow this
        al.add(10); 

        String s1 = (String)al.get(0);
        String s2 = (String)al.get(1);
        String s3 = (String)al.get(2);
    }
}
```

**Output:**

```java
15: error: no suitable method found for add(int)
        al.add(10); 
          ^
```

**3。不需要单独的类型转换**:如果我们不使用泛型，那么在上面的例子中，每次我们从数组列表中检索数据时，我们都必须对其进行类型转换。每次检索操作中的类型转换都是一个大问题。如果我们已经知道我们的列表只保存字符串数据，那么我们不需要每次都进行类型转换。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// We don't need to typecast individual members of ArrayList
import java.util.*;

class Test
{
    public static void main(String[] args)
    {
        // Creating a an ArrayList with String specified
        ArrayList <String> al = new ArrayList<String> ();

        al.add("Sachin");
        al.add("Rahul");

        // Typecasting is not needed 
        String s1 = al.get(0);
        String s2 = al.get(1);
    }
}
```

**4。**泛型提升了代码的可重用性。
T3【5。实现泛型算法:通过使用泛型，我们可以实现适用于不同类型对象的算法，同时它们也是类型安全的。

**参考文献:**
[https://docs . Oracle . com/javase/tutorial/Java/generics/why . html](https://docs.oracle.com/javase/tutorial/java/generics/why.html)
本文由 **Dharmesh Singh** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息