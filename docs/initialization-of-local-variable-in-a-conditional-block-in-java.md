# Java 中条件块中局部变量的初始化

> 原文:[https://www . geesforgeks . org/Java 条件块中局部变量的初始化/](https://www.geeksforgeeks.org/initialization-of-local-variable-in-a-conditional-block-in-java/)

Java 包含 5 个条件块，即 if、switch、while、for 和 try。
在所有这些块中，如果指定条件为真，则执行块内的代码，反之亦然。此外，Java 编译器不会让您不初始化局部变量。

在条件块内部初始化局部变量时，必须记住以下 3 个细节:
1。如果指定的条件为真，并且条件中提供了“值”，则程序编译正常。
2。如果指定的条件为真，但条件中提供了“变量”，我们会得到一个编译错误。
3。如果指定的条件为假，我们会得到一个编译错误。

对于基元和引用类型的局部变量，上面给出的几点都是正确的。

示例:
下面的代码会给出一个编译错误。

```java
// Java program to demonstrate error if we
// assign value to an uninitialized variable
// only in if block.
public class InitTesting {
    public static void main(String args[])
    {
        int i = 100;
        int j;

        // Note that the condition is false
        if (i > 500) 
            j = i + 5;

        System.out.println("j :" + j);
    }
}
```

```java
 Output: 
prog.java:8: error: variable j might not have been initialized
        System.out.println("j :" + j);
                                   ^
1 error

```

if 语句中的条件为 false。因此，局部变量“j”永远不会被初始化。因此，试图引用第 8 行中未初始化的变量“j”会产生编译错误。
为了避免这种情况，在条件块之外将局部变量初始化为默认值。
下面的代码工作正常-

```java
// Java program to demonstrate that the above
// error is gone if we initialize the variable.
public class InitTesting {
    public static void main(String args[])
    {
        int i = 100;
        int j = 0;

        // Note that the condition is false
        if (i > 500) {
            j = i + 5;
        }
        System.out.println("j :" + j);
    }
}
```

```java
 Output:
j :0

```

此外，在 Java 中，“值”是在编译时读取的。但是，“变量”是在运行时读取的。因此，当变量是条件的一部分，而另一个变量在条件块中被初始化时，它会给出一个意外的编译时错误。

示例:看看下面的代码:

```java
// Java program to demonstrate error even if
// condition is true.

class Test {
    public static void main(String args[])
    {
        int a = 90;
        int b = 80;
        int i;

        // The condition is true
        if (a > b) {
            i = a + 5;
        }
        System.out.println("i :" + i);
    }
}
```

```java
 Output:
prog.java:9: error: variable i might not have been initialized
        System.out.println("i :" + i);
                                   ^
1 error

```

不管条件是真还是假，它都会给出一个编译错误，因为 Java 在编译时没有读取变量，因此“I”没有初始化。

另一方面，如果指定的是值而不是变量，这种情况就不会发生。

```java
// Java program to demonstrate that there is
// no error if we constants in if condition.
class Test {
    public static void main(String args[])
    {
        int i;
        if (90 > 80) {
            i = a + 5;
        }
        System.out.println("i :" + i);
    }
}
```

```java
 Output:
i :95

```