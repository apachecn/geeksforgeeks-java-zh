# Java 中的最终静态变量

> 原文:[https://www.geeksforgeeks.org/final-static-variable-java/](https://www.geeksforgeeks.org/final-static-variable-java/)

先决条件:[静态变量](https://www.geeksforgeeks.org/static-keyword-in-java/)、[最终关键字](https://www.geeksforgeeks.org/final-keyword-java/)

**静态变量:**当一个变量的值没有变化时，那么去做实例变量就不是一个好的选择。届时，我们可以向该变量添加静态修饰符。每当我们将变量声明为静态时，就会在类级别创建一个与对象共享的变量。静态变量中任何变化都会反映到其他对象的操作中。如果我们不初始化静态变量，那么缺省情况下，JVM 将为静态变量提供一个默认值。

但是当我们用 final 修饰符声明一个静态变量时，我们应该注意以下约定:

*   Simply declaring variables static will cause their values to be changed by one or more instances of the class that declares them.
*   Declaring them as static finals will help you create a **constant** . There is only one copy of the variable that cannot be reinitialized.

**关于最终静态变量的要点:**

1.  **Initialization of variable Mandatory** : If the static variable declared as final, then we have to perform initialization explicitly whether we are using it or not and JVM won’t provide any default value for the final static variable.

    ```java
    // Java program to illustrate the behavior of
    // final static variable
    class Test {
        final static int x;
        public static void main(String[] args)
        {
        }
    }
    ```

    输出:

    ```java
    error: variable x not initialized in the default constructor

    ```

2.  **类加载前初始化**:对于最终静态变量，强制要求我们在类加载完成前进行初始化。我们可以在声明时初始化一个最终的静态变量。

    ```java
    // Java program to illustrate that final
    // static variable can be initialized
    // at the time of declaration
    class Test {
        final static int x = 10;
        public static void main(String[] args)
        {
            System.out.println(x);
        }
    }
    ```

    输出:

    ```java
    10

    ```

3.  **在静态块内部初始化**:我们也可以在静态块内部初始化一个最终的静态变量，因为我们应该在类之前初始化一个最终的静态变量，而且我们知道静态块是在 main()方法之前执行的。

    ```java
    // Java program to illustrate that final
    // static variable can be initialized
    // inside static block
    class Test {
        final static int x;
        static
        {
            x = 10;
        }
        public static void main(String[] args)
        {
            System.out.println(x);
        }
    }
    ```

    输出:

    ```java
    10

    ```

除了上面提到的方法，如果我们试图在其他地方初始化一个最终的静态变量，那么我们会得到编译时错误。

```java
// Java program to illustrate
// that we can't declare
// final static variable
// within any non-static blocks or methods
class Test {
    final static int x;
    public static void m()
    {
        x = 10;
    }
    public static void main(String[] args)
    {
        System.out.println(x);
    }
}
```

输出:

```java
error: cannot assign a value to final variable x

```

**最终静态变量**的实现

```java
class MainClass {
    final static String company = "GFG";
    String name;
    int rollno;
public
    static void main(String[] args)
    {
        MainClass ob = new MainClass();

        // If we create a database for GFG org
        // then the company name should be constant
        // It can’t be changed by programmer.
        ob.company = "Geeksforgeeks";

        ob.name = "Bishal";
        ob.rollno = 007;
        System.out.println(ob.company);
        System.out.println(ob.name);
        System.out.println(ob.rollno);
    }
}
```

输出:

```java
error: cannot assign a value to final variable company

```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。