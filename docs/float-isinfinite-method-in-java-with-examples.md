# Java 中的 Float isInfinite()方法，带示例

> 原文:[https://www . geesforgeks . org/float-is infinity-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-isinfinite-method-in-java-with-examples/)

[**Float 类**](https://www.geeksforgeeks.org/java-lang-float-class-in-java/) 中的**IsInfinish()**方法是 Java 中的一个内置方法，如果这个 Float 值或指定的 Float 值在数量级上无限大，则返回 true，否则返回 false。
**语法:**

```
public boolean isInfinite()
        or
public static boolean isInfinite(float val)
```

**参数**:该函数接受单个参数**值**，该值指定了当直接使用浮点类作为静态方法调用时要检查的值。当方法用作实例方法时，参数不是必需的。
**返回值:**返回**真**如果值为无穷大，则返回**假**。
下面的程序说明了 Java 中的*isInfinite()*方法:
**程序 1:** 使用静态 IsInfinity()方法

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate
// Float isInfinite() method
// without parameter

class GFG {
    public static void main(String[] args)
    {

        // first example
        Float f1 = new Float(1.0 / 0.0);

        boolean res = f1.isInfinite();

        // printing the output
        if (res)
            System.out.println(f1
                               + " is infinity");
        else
            System.out.println(f1
                               + " is not infinity");

        // second example
        f1 = new Float(0.0 / 0.0);

        res = f1.isInfinite();

        // printing the output
        if (res)
            System.out.println(f1
                               + " is infinity");
        else
            System.out.println(f1
                               + " is not infinity");
    }
}
```

**Output:** 

```
Infinity is infinity
NaN is not infinity
```

**程序 2:** 使用非静态 isFinity()方法

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate
// Float isInfinite() method
// with parameter

class GFG {
    public static void main(String[] args)
    {

        // first example
        Float f1 = new Float(1.0 / 0.0);

        boolean res = f1.isInfinite(f1);

        // printing the output
        if (res)
            System.out.println(f1
                               + " is infinity");
        else
            System.out.println(f1
                               + " is not infinity");

        // second example
        f1 = new Float(0.0 / 0.0);

        res = f1.isInfinite(f1);

        // printing the output
        if (res)
            System.out.println(f1
                               + " is infinity");
        else
            System.out.println(f1
                               + " is not infinity");
    }
}
```

**Output:** 

```
Infinity is infinity
NaN is not infinity
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # IsInfinin()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#isInfinite())