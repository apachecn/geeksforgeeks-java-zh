# Java 中的 IntUnaryOperator 接口

> 原文:[https://www . geeksforgeeks . org/intunaryooperator-in-interface-in-Java/](https://www.geeksforgeeks.org/intunaryoperator-interface-in-java/)

**intrinaryooperator 接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程。](https://www.geeksforgeeks.org/functional-programming-paradigm/)表示接受一个参数并对其进行运算的函数。它的参数和返回类型都是 int 数据类型。这与使用类型为[的对象](https://www.geeksforgeeks.org/unaryoperator-interface-in-java/)和<整数>非常相似。

分配给 IntUnaryOperator 类型的对象的 lambda 表达式用于定义其 **applyAsInt()** ，该表达式最终对其参数应用给定的操作。

### 嵌入式操作界面中的功能

IntUnaryOperator 界面由以下功能组成:

### 1.身份()

这个方法返回一个 IntUnaryOperator，它接受一个 int 值并返回它。返回的 IntUnaryOperator 不对其唯一值执行任何操作。

**语法:**

```
static  IntUnaryOperator identity()
```

**参数:**该方法不接受任何参数

**返回:**取一个值并返回的整数运算器。

下面是说明 identity()方法的代码:

**程序**

```
import java.util.function.IntUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        IntUnaryOperator op = IntUnaryOperator.identity();
        System.out.println(op.applyAsInt(12));
    }
}
```

**Output:**

```
12

```

### 2.applyAsInt()

这个方法接受一个 int 值，执行给定的操作并返回一个 int 值结果。

**语法:**

```
int applyAsInt(int operand)
```

**参数:**该方法接受一个整数值参数

**返回:**:返回一个整型值的结果。

下面是说明 applyAsInt()方法的代码:

```
import java.util.function.IntUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        IntUnaryOperator op = a -> 2 * a;
        System.out.println(op.applyAsInt(12));
    }
}
```

**Output:**

```
24

```

### 3.添加然后()

它返回一个复合的 IntUnaryOperator，其中参数化运算符将在第一个运算符之后执行。如果任一操作引发错误，它将被传递给组合操作的调用方。

**语法:**

```
default IntUnaryOperator andThen(IntUnaryOperator after)
```

**参数:**该方法接受一个参数，该参数之后是当前操作之后要应用的操作。

**返回值:**这个方法返回一个复合的 IntUnaryOperator，它先应用当前操作，然后应用后操作。

**异常:**如果 after 操作为空，则该方法抛出 NullPointerException。

下面是说明 addThen()方法的代码:

**程序 1:**

```
import java.util.function.IntUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        IntUnaryOperator op = a -> 2 * a;
        op = op.andThen(a -> 3 * a);
        System.out.println(op.applyAsInt(12));
    }
}
```

**Output:**

```
72

```

**程序 2:** 演示何时返回 NullPointerException。

```
import java.util.function.IntUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        IntUnaryOperator op = a -> 2 * a;
        op = op.andThen(null);
        System.out.println(op.applyAsInt(12));
    }
}
```

**Output:**

```
java.lang.NullPointerException

```

### 4.撰写()

它返回一个合成的 IntUnaryOperator，其中参数化操作将首先执行，然后是第一个。如果任一操作引发错误，它将被传递给组合操作的调用方。

**语法:**

```
default IntUnaryOperator compose(IntUnaryOperator before)
```

**参数:**此方法接受一个参数，在此参数之前先应用操作，然后应用当前操作

**返回值:**这个方法返回一个复合的 IntUnaryOperator，在参数化运算符之后应用当前运算符

**异常:**如果 before 操作为空，则此方法引发 NullPointerException。

下面是说明 compose()方法的代码:

**程序 1:**

```
import java.util.function.IntUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        IntUnaryOperator op = a -> a / 3;
        op = op.compose(a -> a * 6);
        System.out.println(op.applyAsInt(12));
    }
}
```

**Output:**

```
24

```

**程序 2:** 演示何时返回 NullPointerException。

```
import java.util.function.IntUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        IntUnaryOperator op = a -> a / 3;
        op = op.compose(null);
        System.out.println(op.applyAsInt(12));
    }
}
```

**Output:**

```
java.lang.NullPointerException

```