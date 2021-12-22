# Java 程序演示静态内部类的使用

> 原文:[https://www . geesforgeks . org/Java-program-to-图解-使用静态内部类/](https://www.geeksforgeeks.org/java-program-to-illustrates-use-of-static-inner-class/)

内部类意味着一个类是另一个类的成员。java 中基本上有四种类型的内部类。

1.  嵌套内部类
2.  方法本地内部类
3.  匿名内部类
4.  静态嵌套类

Java 还允许在另一个类中定义一个类。这些被称为嵌套类。定义嵌套类的类称为外部类。与顶级类不同，内部类可以是静态的。非静态嵌套类也称为内部类。在本文中，我们将在 java 程序中实现一个静态内部类。

**示例 1:** 创建静态内部类的实例，稍后调用其方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrates Use of Static Inner Class

// Outer class
public class Gfg {

    // Display message of inner class
    static String msg = "GeeksForGeeks";

    // Static Inner Class
    static class InnerClass {

        // Static Inner Class Method
        public void display()
        {
            // Display message of inner class
            System.out.println("Welcome to " + msg);
        }
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an instance of the static inner class
        InnerClass instance = new InnerClass();

        // Calling method display through
        // the inner class instance variable
        instance.display();
    }
}
```

**输出:**

```
Welcome to GeeksForGeeks
```

**示例 2:** 创建外部类的实例并调用静态内部类方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrates Use of Static Inner Class

// Outer class
public class GFG {

    // Static string message
    static String msg = "GeeksForGeeks";

    // Static Inner Class
    static class InnerClass {

        // Static Inner Class Method
        public void display()
        {
            // Display message in inner class
            System.out.println("Welcome to " + msg);
        }
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an instance of the outer class
        Gfg.InnerClass instance = new Gfg.InnerClass();

        // Calling method of static inner class through
        // the outer class instance variable
        instance.display();
    }
}
```

**输出:**

```
Welcome to GeeksForGeeks
```