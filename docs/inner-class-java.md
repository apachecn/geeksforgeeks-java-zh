# Java 中的内部类

> 原文:[https://www.geeksforgeeks.org/inner-class-java/](https://www.geeksforgeeks.org/inner-class-java/)

在 Java 中，内部类指的是在类或接口内部声明的类，主要介绍的是，总结来说，与 Java 相同的逻辑上相关的类是纯面向对象的，因此使它更接近现实世界。现在，极客们，你们一定想知道他们为什么被介绍进来？

**与内部类相关联的某些优势如下:**

*   Make the code clean and readable.
*   Private methods of external classes can be accessed, which brings a new dimension and makes it closer to the real world.
*   Optimize the code module.

> 在 java 面向对象编程中，我们确实经常使用它们，在 Java 面向对象编程中，我们希望执行某些操作，授予对有限类的访问权限，以及更多，这将在我们讨论和实现 Java 中所有类型的内部类时变得清楚。

### **内部类的类型**

java 中基本上有四种类型的内部类。

1.  嵌套内部类
2.  方法本地内部类
3.  静态嵌套类
4.  匿名内部类

让我们在一个干净的 java 程序旁边依次深入讨论上面的每一种类型，它在每一步都非常重要，因为随着我们坚持向前，它变得非常棘手。

**类型 1:** 嵌套内部类

它可以访问外部类的任何私有实例变量。像任何其他实例变量一样，我们可以拥有访问修饰符 private、protected、public 和 default 修饰符。像类一样，接口也可以嵌套，并且可以有访问说明符。

**示例 1A**

## Java

```
// Java Program to Demonstrate Nested class 

// Class 1
// Helper classes
class Outer {

    // Class 2
    // Simple nested inner class
    class Inner {

        // show() method of inner class
        public void show()
        {

            // Print statement
            System.out.println("In a nested class method");
        }
    }
}

// Class 2
// Main class
class Main {

    // Main driver method
    public static void main(String[] args)
    {

        // Note how inner class object is created inside
        // main()
        Outer.Inner in = new Outer().new Inner();

        // Calling show() method over above object created
        in.show();
    }
}
```

**输出**

```
In a nested class method
```

> **注意:**我们不能在嵌套的内部类中有静态方法，因为内部类隐式地与其外部类的对象相关联，所以它不能为自己定义任何静态方法。例如，下面的程序不编译。

**例 1B**

## 爪哇

```
// Java Program to Demonstrate Nested class 
// Where Error is thrown

// Class 1
// Outer class
class Outer {

    // Method defined inside outer class
    void outerMethod()
    {

        // Print statement
        System.out.println("inside outerMethod");
    }

    // Class 2
    // Inner class
    class Inner {

        // Main driver method
        public static void main(String[] args)
        {

            // Display message for bettr readability
            System.out.println("inside inner class Method");
        }
    }
}
```