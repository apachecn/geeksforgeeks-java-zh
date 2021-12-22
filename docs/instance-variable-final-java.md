# Java 中作为最终变量的实例变量

> 原文:[https://www.geeksforgeeks.org/instance-variable-final-java/](https://www.geeksforgeeks.org/instance-variable-final-java/)

**实例变量:**众所周知，当变量的值因对象而异时，这种类型的变量称为实例变量。实例变量在类中声明，但不在任何方法、构造函数、块等中声明。如果我们不初始化一个实例变量，那么 JVM 会根据该实例变量的数据类型自动提供默认值。
但是如果我们将一个实例变量声明为 **[final](https://www.geeksforgeeks.org/final-keyword-java/)** ，那么我们必须注意实例变量的行为。

*   没有要求将变量设为最终值。然而，当您明确表示永远不会更改变量时，将它设为最终变量通常是一个很好的做法
*   在创建[不可变类时，我们必须使用实例变量作为最终变量。](https://www.geeksforgeeks.org/create-immutable-class-java/)

**关于最终实例变量的要点:**

1.  **Initialization of variable Mandatory :** If the instance variable declared as final, then we have to perform initialization explicitly whether we are using it or not and JVM won’t provide any default value for the final instance variable.

    ```java
    // Java program to illustrate the behavior 
    // of final instance variable
    class Test {
        final int x;
        public static void main(String[] args)
        {
            Test t = new Test();
            System.out.println(t.x);
        }
    }
    ```

    输出:

    ```java
    error: variable x not initialized in the default constructor

    ```

2.  **Initialization before constructor completion :** For final instance variable we have to perform initialization before constructor completion. We can initialize a final instance variable at the time of declaration.

    ```java
    // Java program to illustrate that 
    // final instance variable
    // should be declared at the 
    // time of declaration
    class Test {
        final int x = 10;
        public static void main(String[] args)
        {
            Test t = new Test();
            System.out.println(t.x);
        }
    }
    ```

    输出:

    ```java
    10

    ```

3.  **Initialize inside a non-static or instance block :** We can also initialize a final instance variable inside a non-static or instance block also.

    ```java
    // Java program to illustrate 
    // that final instance variable
    // can be initialize within instance block
    class Test {
        final int x;
        {
            x = 10;
        }
        public static void main(String[] args)
        {
            Test t = new Test();
            System.out.println(t.x);
        }
    }
    ```

    输出:

    ```java
    10

    ```

4.  **Initialization in default constructor :** Inside default constructor we can also initialize a final instance variable.

    ```java
    // Java program to illustrate that 
    // final instance variable
    // can be initialized 
    // in the default constructor
    class Test {
        final int x;
        Test()
        {
            x = 10;
        }
        public static void main(String[] args)
        {
            Test t = new Test();
            System.out.println(t.x);
        }
    }
    ```

    输出:

    ```java
    10

    ```

上面提到的是执行最终实例变量初始化的唯一可能的地方。如果我们试图在其他任何地方执行初始化，那么我们将得到编译时错误。

```java
// Java program to illustrate 
// that we cant declare
// final instance variable 
// within any static blocks
class Test {
    final int x;
    public static void main(String[] args)
    {
        x = 10;
        Test t = new Test();
        System.out.println(t.x);
    }
}
```

输出:

```java
error: non-static variable x cannot be referenced from a static context

```

```java
// Java program to illustrate that we
//  cant declare or initialize
// final instance variable within any methods
class Test {
    final int x;
    public void m()
    {
        x = 10;
    }
}
```

输出:

```java
error: cannot assign a value to final variable x

```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论