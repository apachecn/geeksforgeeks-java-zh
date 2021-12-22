# Java 中的 Double 有限()方法，带示例

> 原文:[https://www . geeksforgeeks . org/double-is infinitial-method-in-Java-with-examples/](https://www.geeksforgeeks.org/double-isinfinite-method-in-java-with-examples/)

[java Double 类](https://www.geeksforgeeks.org/java-lang-double-class-java/)的**Java . lang . Double . IsInfinish()**方法是 Java 中的内置方法，如果该 Double 值或指定的 Double 值在数量级上无限大，则返回 true，否则返回 false。

**语法**:

```java
public boolean isInfinite()
        or
public static boolean isInfinite(double val)
```

**参数**:该函数接受单个参数**值**，该值指定了当直接使用 Double 类作为静态方法调用时要检查的值。当方法用作实例方法时，参数不是必需的。
**返回值:**返回**真**如果值为无穷大，则返回**假**。
下面的程序说明了 Java 中的*IsInfinin()*方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate
// Double isInfinite() method
// without parameter

class GFG {
    public static void main(String[] args)
    {

        // first example
        Double f1 = new Double(1.0 / 0.0);

        boolean res = f1.isInfinite();

        // printing the output
        if (res)
            System.out.println(f1 + " is infinity");
        else
            System.out.println(f1 + " is not infinity");

        // second example
        f1 = new Double(0.0 / 0.0);

        res = f1.isInfinite();

        // printing the output
        if (res)
            System.out.println(f1 + " is infinity");
        else
            System.out.println(f1 + " is not infinity");
    }
}
```

**Output:** 

```java
Infinity is infinity
NaN is not infinity
```