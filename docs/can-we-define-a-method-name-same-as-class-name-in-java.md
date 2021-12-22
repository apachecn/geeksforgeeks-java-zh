# 我们可以在 Java 中定义一个与类名相同的方法名吗？

> 原文:[https://www . geesforgeks . org/can-we-define-a-method-name-as-class-name-in-Java/](https://www.geeksforgeeks.org/can-we-define-a-method-name-same-as-class-name-in-java/)

在 Java 中，我们可以有一个与类名相同的方法名，但是这样做并不是一个好的做法。这个概念可以通过例子而不是解释来阐明。在下面的例子中，当一个对象被创建并且一个同名的方法被使用 **obj 调用时，一个默认的构造函数被调用。Main()** 。

**例 1**:

T5】JavaT7

```
// Java program to demonstrate that a method
// can have same name as a Constructor or
// class name

import java.io.*;

public class Main {
    void Main()
    {
        System.out.println(
            "My name is same as Constructor name!");
    }
    public static void main(String[] args)
    {
          // create an object of class
          // Main
        Main obj = new Main();

          // call the method
        obj.Main();
    }
}
```

T8T10**输出**T1

**例 2:** 要检查是否真的显示了构造函数属性，我们可以这样检查。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// checking whether a method is acting like a
// constructor or just a method

import java.io.*;

public class Main {

    // default constructor
    Main() { this(5); }
    /*
      Main(int a) {
        System.out.println(a);
      }
    */

    // Just a method
    // not a parameterized constructor
    void Main(int a)
    {
        System.out.println("I am a method");
    }

    public static void main(String[] args)
    {
        // create an object
        Main obj = new Main();

          // obj.Main();
    }
}
```

**错误:**

```
error: constructor Main in class Main cannot be applied to given types;
    Main() { this(5); }
             ^
  required: no arguments
  found: int
  reason: actual and formal argument lists differ in length
1 error
```

这里我们不通过一个对象调用 **void Main(int)** ，而是通过**调用这个(int)** 及其显示错误，所以这不能是一个构造函数。这会给你一个错误，显示没有参数化的构造函数可用，但是我们认为我们已经有了它，那就是 **void Main(int a)** 。但是 void Main(int a)的行为并不是为了证明删除上面代码中的注释部分就可以了。

## Java

```
// Java program to demonstrate that
// constructor is different from method

import java.io.*;

public class Main {

    // default constructor
    Main() { this(5); }

    // parameterized constructor
    Main(int a) { System.out.println(a); }

    // method but not a constructor
    void Main(int a)
    {
        System.out.println(
            "I am just a method, not  a constructor");
    }

    public static void main(String[] args)
    {
        Main obj = new Main();
        // obj.Main();
    }
}
```

**输出**

```
5
```

**例 3:**

## Java

```
// Java program to demonstrate
// checking whether a method is acting like a
// constructor or just a method

import java.io.*;

public class Main {
    // default constructor
    Main() { System.out.println("Hey"); }

    // method, not a constructor
    void Main()
    {
        System.out.println("I can have return type too.");
    }

    public static void main(String[] args)
    {

        // create an object
        Main obj = new Main();
    }
}
```

**输出**

```
Hey
```

最后，我们可以得出结论，当我们有一个与类名同名的方法的返回类型时，那么它就失去了构造函数所拥有的特性，并且会表现得像一个方法。这是编程中的一种糟糕做法。