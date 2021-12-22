# Java 中的双元运算符接口

> 原文:[https://www . geesforgeks . org/double unaryooperator-interface-in-Java/](https://www.geeksforgeeks.org/doubleunaryoperator-interface-in-java/)

**双元运算符接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程。](https://www.geeksforgeeks.org/functional-programming-paradigm/)表示接受一个参数并对其进行运算的函数。它的参数和返回类型都是双数据类型。这与使用类型为[的对象](https://www.geeksforgeeks.org/unaryoperator-interface-in-java/)一个操作符<双>非常相似。

分配给双元运算符类型的对象的 lambda 表达式用于定义其**applyastdouble()**，该表达式最终会对其参数应用给定的操作。

### 双元运算符接口中的函数

双元运算符接口由以下功能组成:

### 1.身份()

这个方法返回一个双精度运算符，它接受一个双精度值并返回。返回的双元运算符不对其唯一值执行任何操作。

**语法:**

```java
static  DoubleUnaryOperator identity()
```

**参数:**该方法不接受任何参数

**返回:**取一个值并返回的双元运算符。

下面是说明 identity()方法的代码:

**程序**

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        DoubleUnaryOperator
            op
            = DoubleUnaryOperator.identity();

        System.out.println(op.applyAsDouble(12.0));
    }
}
```

**Output:**

```java
12.0

```

### 2.applyAsDouble()

此方法接受一个双精度值，执行给定的操作并返回一个双精度值结果。

**语法:**

```java
double applyAsDouble(double operand)
```

**参数:**该方法采用一个双值参数

**返回:**:返回一个双值结果。

下面是演示 applyAsDouble()方法的代码:

**程序**

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        DoubleUnaryOperator op = a -> 2 * a;

        System.out.println(op.applyAsDouble(12.0));
    }
}
```

**Output:**

```java
24.0

```

### 3.添加然后()

它返回一个复合的双元运算符，其中参数化运算符将在第一个运算符之后执行。如果任一操作引发错误，它将被传递给组合操作的调用方。

**语法:**

```java
default DoubleUnaryOperator andThen(DoubleUnaryOperator after)
```

**参数:**该方法接受之后的参数**，该参数是当前操作之后要应用的操作。**

**返回值:**该方法返回一个由**组成的双元运算符**，该运算符先应用当前操作，然后应用后操作。

**异常:**如果后操作为空，该方法抛出**空指针异常**。

下面是说明 addThen()方法的代码:

**程序 1:**

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        DoubleUnaryOperator op = a -> 2 * a;

        op = op.andThen(a -> 3 * a);

        System.out.println(op.applyAsDouble(12.0));
    }
}
```

**Output:**

```java
72.0

```

**程序 2:** 演示何时返回 NullPointerException。

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        try {
            DoubleUnaryOperator op = a -> 2 * a;

            op = op.andThen(null);

            System.out.println(op.applyAsDouble(12.0));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.NullPointerException

```

### 4.撰写()

它返回一个复合的双元运算符，其中参数化操作将首先执行，然后是第一个。如果任一操作引发错误，它将被传递给组合操作的调用方。

**语法:**

```java
default DoubleUnaryOperator compose(DoubleUnaryOperator before)
```

**参数:**该方法在之前接受一个参数**，该参数是先应用的操作，然后是当前操作**

**返回值:**这个方法返回一个复合的双元运算符，在参数化运算符之后应用当前运算符

**异常:**如果之前的操作为空，该方法抛出**空指针异常**。

下面是说明 compose()方法的代码:

**程序 1:**

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        DoubleUnaryOperator op = a -> a / 3;

        op = op.compose(a -> a * 6);

        System.out.println(op.applyAsDouble(12.0));
    }
}
```

**Output:**

```java
24.0

```

**程序 2:** 演示何时返回 NullPointerException。

```java
import java.util.function.DoubleUnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        try {
            DoubleUnaryOperator op = a -> a / 3;

            op = op.compose(null);

            System.out.println(op.applyAsDouble(12.0));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.NullPointerException

```