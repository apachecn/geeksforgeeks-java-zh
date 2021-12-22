# 【Java 对象是如何存储在内存中的？

> 原文:[https://www.geeksforgeeks.org/g-fact-46/](https://www.geeksforgeeks.org/g-fact-46/)

在 Java 中，所有对象都是在堆上动态分配的。这与 C++不同，在 c++中，对象可以在堆栈或堆上分配内存。在 C++中，当我们使用 new()分配对象时，对象是在 Heap 上分配的，如果不是全局的或静态的，则在 Stack 上分配。
在 Java 中，当我们只声明一个类类型的变量时，只创建一个引用(不为对象分配内存)。要为对象分配内存，我们必须使用 new()。所以对象总是在堆上分配内存(更多细节见[这个](https://docs.oracle.com/cd/E13150_01/jrockit_jvm/jrockit/geninfo/diagnos/garbage_collect.html))。
例如，以下程序编译失败。编译器给出错误*“这里出错是因为 t 没有初始化”。*

## Java 语言（一种计算机语言，尤用于创建网站）

```java
class Test {

// class contents
void show()
{
    System.out.println("Test::show() called");
}
}

public class Main {

        // Driver Code
    public static void main(String[] args)
    {
        Test t;

        // Error here because t
        // is not initialized
        t.show();
    }
}
```

使用 new()分配内存可以使上述程序工作。

## Java 语言（一种计算机语言，尤用于创建网站）

```java
class Test {

// class contents
void show()
{
    System.out.println("Test::show() called");
}
}

public class Main {

    // Driver Code
    public static void main(String[] args)
    {

        // all objects are dynamically
        // allocated
        Test t = new Test();
        t.show(); // No error
    }
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。