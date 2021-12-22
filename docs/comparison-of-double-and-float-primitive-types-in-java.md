# Java 中双精度和浮点基元类型的比较

> 原文:[https://www . geesforgeks . org/Java 中双精度浮点基元类型的比较/](https://www.geeksforgeeks.org/comparison-of-double-and-float-primitive-types-in-java/)

考虑 Java 中的以下两个代码:

```java
// This program prints true
class Geeksforgeeks {
  public static void main(String args[]) {
    float f = 5.25f;
    double d = 5.25
    System.out.println(f == d);
  }
}
```

**输出**

```java
true
```

```java
// But this program prints false.
class Geeksforgeeks {
  public static void main(String args[]) {
    float f = 5.1f;
    double d = 5.1;
    System.out.println(f == d);
  }
}
```

**输出**

```java
false
```

输出在第一个示例中为真，在第二个示例中为假。我们知道浮点和双精度是不同的。浮点数[尾数](https://www.geeksforgeeks.org/floating-point-representation-digital-logic/)的大小为 24，双精度为 53。

让我们考虑 5.25 的第一个例子。整数部分的二进制表示为 101，点的一部分的二进制表示为 0.01(只需要两位)

让我们考虑第二个例子 5.1。整数部分的二进制表示是相同的。但是 0.1 的二进制表示是 1/16 + 1/32 + 1/64 + 1/128 …..以此类推，直到我们到达尾数的末尾或者总和变得大于 0.1。在这种情况下，我们到达尾数的末尾，因此 5.1 的值在 float 和 double 中变得不同。