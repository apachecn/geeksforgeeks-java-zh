# 在 Java 中为静态最终变量赋值

> 原文:[https://www.geeksforgeeks.org/g-fact-55/](https://www.geeksforgeeks.org/g-fact-55/)

**在 Java 中为静态最终变量赋值:**
在 Java 中，非静态最终变量可以在构造函数中赋值，也可以在声明中赋值。但是，静态最终变量不能在构造函数中赋值；必须在声明中为它们赋值。
例如，以下程序工作正常。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Test {

    // i could be assigned a value here
    // or constructor or init block also.
    final int i;
    Test()
    {
        i = 10;
    }

    // other stuff in the class
}
```

如果我们将 *i* 设为*静态最终*，那么我们必须在声明中为 I 赋值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Test {

    // Since i is static final,
    // it must be assigned value here
    // or inside static block .
    static final int i;
    static
    {
        i = 10;
    }

    // other stuff in the class
}
```

这种行为是显而易见的，因为静态变量在一个类的所有对象之间共享；创建一个新对象会改变相同的静态变量，如果静态变量是 final，这是不允许的。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。