# 将字符串转换为对象的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-转换-字符串-对象/](https://www.geeksforgeeks.org/java-program-to-convert-string-to-object/)

内置的**对象类**是所有类的父类，即每个类在内部都是对象类的子类。所以我们可以直接给一个对象赋值一个字符串。

基本上，有两种方法可以将字符串转换为对象。下面是使用这两种方法将字符串转换为对象。

1.  使用赋值运算符
2.  使用 Class.forName()方法

**方法 1:使用赋值运算符**

一个 [**赋值运算符**](https://www.geeksforgeeks.org/java-assignment-operator-with-examples/) 将字符串赋给对象类的引用变量。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert string to an object
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // string
        String s = "GeeksForGeeks";

        // assigning string to an object
        Object object = s;

        // to check the data-typeof the object 
        // to confirm that s has been stored in object
       System.out.println("Datatype of the variable in object is : "
                          +object.getClass().getName());

       System.out.println("object is : "+object);
    }
}
```

**Output**

```java
Datatype of the variable in object is : java.lang.String
object is : GeeksForGeeks
```

**方法二:使用 Class.forName()方法**

我们还可以使用**[**class . FOrname()**](https://www.geeksforgeeks.org/class-forname-method-in-java-with-examples/)方法将字符串转换为对象。**

****语法:****

```java
public static Class<T> forName(String className) throws ClassNotFoundException
```

****参数:**该方法接受参数**类名**，这是需要其实例的类。**

****返回值:**该方法返回指定类名的这个类的实例。**

*   **Class 类属于 java.lang 包。**
*   **java.lang.Class 类有一个方法 [getSuperclass()](https://www.geeksforgeeks.org/class-getsuperclass-method-in-java-with-examples/) 。它用于检索当前类的超类。此方法返回一个类对象，该对象代表调用该方法的类对象的超类。如果在对象类上调用该方法，那么它将返回空值，因为对象类是类层次结构中最顶层的类，并且不能有任何对象类的超类。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to convert the string to an object

class GFG {
    public static void main(String[] args) throws Exception
    {
        // getting the instance of the class passed in
        // forName method as a string
        Class c = Class.forName("java.lang.String");

        // getting the name of the class
        System.out.println("class name: " + c.getName());

        // getting the name of the super class
        System.out.println("super class name: "
                           + c.getSuperclass().getName());
    }
}
```

****Output**

```java
class name: java.lang.String
super class name: java.lang.Object
```**