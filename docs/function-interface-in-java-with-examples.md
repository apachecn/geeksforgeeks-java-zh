# Java 中的函数接口，示例

> 原文:[https://www . geesforgeks . org/function-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/)

**函数接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个接受一个参数并产生一个结果的函数。因此，这个功能接口采用了两个泛型，即:

*   **T** :表示输入参数的类型
*   **R** :表示功能的返回类型

> 分配给函数类型对象的 lambda 表达式用于定义其 **apply()** ，该表达式最终将给定函数应用于参数。

### 函数接口中的方法

功能界面由下列 4 种方法组成，这些方法将在后面讨论如下:

1.  应用()
2.  然后()
3.  构成
4.  身份()

**方法 1:** 应用()

**语法:**

```
R apply(T t)
```

**参数:**该方法只接受一个参数 **t** ，即函数参数

**返回类型:**该方法返回类型为 r 的**函数结果**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Functional Interface
// Via apply() method

// Importing interface
import java.util.function.Function;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Function which takes in a number
        // and returns half of it
        Function<Integer, Double> half = a -> a / 2.0;

        // Applying the function to get the result
        System.out.println(half.apply(10));
    }
}
```

**Output**

```
5.0
```

**方法 2:** 然后()

它返回一个组合函数，其中参数化函数将在第一个函数之后执行。如果对任一函数的计算引发错误，它将被传递给组合函数的调用方。

**语法:**

```
default <V> Function<T, V> 
andThen(Function<? super R, ? extends V> after)
```

其中 **V** 是 after 函数和组合函数的输出类型

**参数:**该方法接受之后的参数**，该参数是当前函数之后要应用的函数。\**

**返回值:**该方法返回一个**合成函数**，先应用当前函数，再应用后函数

**异常:**如果 after 函数为空，该方法抛出 **NullPointerException** 。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate addThen() method

// Importing interface
import java.util.function.Function;

// Main class
public class GFG {

    // main driver method
    public static void main(String args[])
    {
        // Function which takes in a number and
        // returns half of it
        Function<Integer, Double> half = a -> a / 2.0;

        // Now treble the output of half function
        half = half.andThen(a -> 3 * a);

        // Applying the function to get the result
        // and printing on console
        System.out.println(half.apply(10));
    }
}
```

**Output**

```
15.0
```

**示例 2:** 演示何时返回 NullPointerException。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate addThen() method
// When NullPointerException occurs

// Importing interface
import java.util.function.Function;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Function which takes in a number and
        // returns half of it
        Function<Integer, Double> half = a -> a / 2.0;

        // Try block to check for exce3ptions
        try {

            // Trying to pass null as parameter
            half = half.andThen(null);
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Print statement
            System.out.println("Exception thrown "
                               + "while passing null: "
                               + e);
        }
    }
}
```

**Output**

```
Exception thrown while passing null: java.lang.NullPointerException
```

**方法 3:** 合成()

它返回一个组合函数，其中参数化函数将首先执行，然后是第一个。如果对任一函数的计算引发错误，它将被传递给组合函数的调用方。

**语法:**

```
default <V> Function<V, R> 
compose(Function<? super V, ? extends T> before)
```

其中 V 是 before 函数和复合函数的输入类型

**参数:**该方法在之前接受一个参数**，该参数是先应用的函数，然后是当前函数**

**返回值:**此方法返回一个组合函数，该函数在参数化函数之后应用当前函数

**异常:**如果 before 函数为空，该方法抛出 [NullPointerException](https://www.geeksforgeeks.org/null-pointer-exception-in-java/) 。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate compose() method

// Importing Function interface
import java.util.function.Function;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Function which takes in a number and
        // returns half of it
        Function<Integer, Double> half = a -> a / 2.0;

        // However treble the value given to half function
        half = half.compose(a -> 3 * a);

        // Applying the function to get the result
        System.out.println(half.apply(5));
    }
}
```

**Output**

```
7.5
```

**示例 2:** 当返回 NullPointerException 时。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate compose() method

// Importing Function interface
import java.util.function.Function;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Function which takes in a number and
        // returns half of it
        Function<Integer, Double> half = a -> a / 2.0;

        // Try bloc kto check for exceptions
        try {

            // Trying to pass null as parameter
            half = half.compose(null);
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Print statement
            System.out.println("Exception thrown "
                               + "while passing null: "
                               + e);
        }
    }
}
```

**Output**

```
Exception thrown while passing null: java.lang.NullPointerException
```

**方法 4:** 同一性()

此方法返回一个只返回其唯一参数的函数。

**语法:**

```
static <T> Function<T, T> identity()
```

其中 **T** 表示参数的类型和要返回的值

**返回:**该方法返回一个**函数**，该函数返回自己的参数

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate identity() method

// Importing Function interface
import java.util.function.Function;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Function which takes in a number and
        // returns it
        Function<Integer, Integer> i = Function.identity();

        // Print statement
        System.out.println(i.apply(10));
    }
}
```

**Output**

```
10
```