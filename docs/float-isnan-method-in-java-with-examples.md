# Java 中 Float isNaN()方法，带示例

> 原文:[https://www . geesforgeks . org/float-isnan-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-isnan-method-in-java-with-examples/)

**[Float 类](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)** 中的 **Float.isNaN()** 方法是 Java 中的内置方法，如果该 Float 值或指定的 Float 值不是数字(NaN)，则返回 true，否则返回 false。

**语法** :

```java
public boolean isNaN()
        or
public static boolean isNaN(float val)
```

**参数**:该函数接受单个参数**值**，该值指定了当直接使用浮点类作为静态方法调用时要检查的值。当方法用作实例方法时，参数不是必需的。

**返回值:**如果值为 *NaN* 则返回 **true** ，否则返回 **false** 。

下面的程序用 Java 说明了 *isNaN()* 方法:

**程序一:**使用静态 isNaN()方法

```java
// Java code to demonstrate
// Float isNaN() method
// without parameter

class GFG {
    public static void main(String[] args)
    {

        // first example
        Float f1 = new Float(1.0 / 0.0);

        boolean res = f1.isNaN();

        // printing the output
        if (res)
            System.out.println(f1 + " is NaN");
        else
            System.out.println(f1 + " is not NaN");

        // second example
        f1 = new Float(0.0 / 0.0);

        res = f1.isNaN();

        // printing the output
        if (res)
            System.out.println(f1 + " is NaN");
        else
            System.out.println(f1 + " is not NaN");
    }
}
```

T5】输出:

```java
Infinity is not NaN
NaN is NaN

```

**程序二:**使用非静态 isNaN()方法

```java
// Java code to demonstrate
// Float isNaN() method
// with parameter

class GFG {
    public static void main(String[] args)
    {

        // first example
        Float f1 = new Float(1.0 / 0.0);

        boolean res = f1.isNaN(f1);

        // printing the output
        if (res)
            System.out.println(f1 + " is NaN");
        else
            System.out.println(f1 + " is not NaN");

        // second example
        f1 = new Float(0.0 / 0.0);

        res = f1.isNaN(f1);

        // printing the output
        if (res)
            System.out.println(f1 + " is NaN");
        else
            System.out.println(f1 + " is not NaN");
    }
}
```

T5】输出:

```java
Infinity is not NaN
NaN is NaN

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # isNaN()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#isNaN())