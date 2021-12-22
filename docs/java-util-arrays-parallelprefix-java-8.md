# Java 8 中的 Java . util . arrays . parallelprefix

> 原文:[https://www . geesforgeks . org/Java-util-arrays-parallelprefix-Java-8/](https://www.geeksforgeeks.org/java-util-arrays-parallelprefix-java-8/)

**先决条件:**

*   [Java 8 中的 Lambda 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)
*   [Java 中的流](https://www.geeksforgeeks.org/stream-in-java/)

java 8 中的[数组类](https://www.geeksforgeeks.org/array-class-in-java/)引入了 parallelPrefix 方法。parallelPrefix 方法对数组的元素累计执行给定的数学函数，它们同时修改数组。
**语法:**

```java
parallelPrefix(int[] array, IntBinaryOperator op)
Parameters :
array : integer array on which operation is to be performed
op : It is of type IntBinaryOperation (It represents an operation upon two int operands
and returns a result of type int)
Exception :
NullPointerException- Throws if the array or function passed as a parameter is null
```

**变化:**T2]

```java
parallelPrefix(double[] array, DoubleBinaryOperator op)
parallelPrefix(double[] array, int fromIndex, int toIndex, DoubleBinaryOperator op)
parallelPrefix(int[] array, IntBinaryOperator op)
parallelPrefix(int[] array, int fromIndex, int toIndex, IntBinaryOperator op)
parallelPrefix(long[] array, int fromIndex, int toIndex, LongBinaryOperator op)
parallelPrefix(long[] array, LongBinaryOperator op)
parallelPrefix(T[] array, BinaryOperator op)
parallelPrefix(T[] array, int fromIndex, int toIndex, BinaryOperator op)
```

让我们用一个例子来理解 **parallelPrefix(int[] array，int binaryoperator op)**
**例子 1:** 它说明了传递第二个参数(即 IntBinaryOperator)
的一些方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate parallelPrefix()
// and demonstrate different ways of
// passing parameter to it
import java.util.Arrays;
import java.util.function.IntBinaryOperator;
public class GFG {

    // Performs addition
    static int compute(int x, int y)
    {
        return x + y;
    }

    public static void main(String[] args) {
        int[] arr = { 2, 1, 7, 8, 4, 5, 6, 9, 8, 7, 1, 2, 3, 6, 5, 4, 7, 5 };

        // Uncomment to see different methods working

        /* Method 1(Creating an instance for IntBinaryOperator)
        //IntBinaryOperator op = (x, y) -> x + y;
        //Arrays.parallelPrefix(arr, op);

        // Method 2(Directly passing a lambda expression that evaluates to
        // return IntBinaryOperator)
        //Arrays.parallelPrefix(arr, (x, y) -> x + y);

        // Method 3(Declaring the operation in some external Function)
        Arrays.parallelPrefix(arr, GFG::compute); */
        Arrays.parallelPrefix(arr, (x,y) -> compute(x,y));

        // Printing the array elements
        Arrays.stream(arr).forEach(e -> System.out.print(e + "   "));
    }
}
```

输出:

```java
2   3   10   18   22   27   33   42   50   57   58   60   63   69   74   78   85   90   
```

正如您在上面的例子中看到的，parallelPrefix 为 IntBinaryOperator 取了两个参数。它执行给定的计算并更新第二个元素，保持第一个元素不变。
**示例 2:** 这里通过 **parallelPrefix(int[] array，IntBinaryOperator op)** 说明了对数组的更多操作，并介绍了 **parallelPrefix(int[] array，int fromIndex，int toIndex，IntBinaryOperator op)** 。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate parallelPrefix
// on a range of a given array

import java.util.Arrays;
import java.util.function.IntBinaryOperator;
public class GFG {

    public static void main(String[] args) {
        int[] arr = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        // Example 1
        // With Primitive types
        // Performs addition with the adjacent element if first is less than
        // second else perform subtraction

        Arrays.parallelPrefix(arr, (x, y) -> {
            if (x < y)
                return x + y;
            else
                return x - y;
        });
        System.out.println("Example 1: with Primitive type");

        // Printing elements of array
        Arrays.stream(arr).forEach(e -> System.out.print(e + "   "));

        int[] arr1 = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        // Example 2
        // With primitives
        // Keeps on multiplying adjacent elements

        Arrays.parallelPrefix(arr1, (x, y) -> x * y);
        System.out.println("\nExample 2: with primitives");

        // Printing elements of array
        Arrays.stream(arr1).forEach(e -> System.out.print(e + "   "));

        // Lets examine parallelPrefix(int[] array, int fromIndex, int toIndex,
        // IntBinaryOperator op)
        // It is used when we want to make changes in the specified range of
        // elements in an array

        // Example:
        // If adjacent elements are even then it replace both the element with
        // first
        int[] arr2 = { 1, 2, 4, 8, 5, 9, 6, 8, 9, 10, 11 };

        Arrays.parallelPrefix(arr2, 2, 8, (x, y) -> {
            if (x % 2 == 0 && y % 2 == 0)
                return x;
            else
                return y;
        });
        System.out.println("\nExample: Making Changes in the "
                            +"specified range of element in an Array");

        // Printing element of array
        Arrays.stream(arr2).forEach(e -> System.out.print(e + "   "));
    }

}
```

输出:

```java
Example 1: with Primitive type
1   3   0   4   9   3   10   2   11   1   
Example 2: with primitives
1   2   6   24   120   720   5040   40320   362880   3628800   
Example: Making Changes in the specified range of element in an Array
1   2   4   4   5   9   6   6   9   10   11   
```

**示例 3 :** 这说明了 **parallelPrefix(T[]数组，BinaryOperator op)** 和
T5】parallelPrefix(T[]数组，int fromIndex，int toIndex，BinaryOperator op)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate parallelPrefix
// on a user defined array
import java.util.Arrays;
import java.util.function.IntBinaryOperator;
public class GFG {

    // User defined class   
    static class Person{
        String name;
        int age;

        //constructor
        Person(String name, int age){
            this.name = name;
            this.age = age;
        }
    }
    public static void main(String[] args) {

        // Working with user defined class
        Person[] p = { new Person("Geek1", 10),
                       new Person("Geek2", 20), new Person("Geek3", 30),
                       new Person("Geek4", 40), new Person("Geek5", 50),
                       new Person("Geek6", 60), };

        // Example 1; Here we convert the first parameter to upper case and then
        // concatenate or add(in case of age) with the second through out the
        // array
        Arrays.parallelPrefix(p, (e1, e2) ->
                            new Person(e1.name.toUpperCase().concat(e2.name),
                                                e1.age + e2.age));
        System.out.println("\nExample 1 :");

        // Printing elements of the array
        Arrays.stream(p).forEach(e -> System.out.println(e.name + "   " + e.age));

        Person[] p1 = { new Person("Geek1", 10),
                        new Person("Geek2", 20), new Person("Geek3", 30),
                        new Person("Geek4", 40), new Person("Geek5", 50),
                    new Person("Geek6", 60), };

        // This illustrates the same modification as described above but within
        // a specified range
        Arrays.parallelPrefix(p1, 1, 4, (e1, e2) ->
                            new Person(e1.name.toUpperCase().concat(e2.name),
                                                e1.age + e2.age));
        System.out.println("\nExample 2 :");

        // Printing elements of array
        Arrays.stream(p1).forEach(e -> System.out.println(e.name + "   " + e.age));
    }

}
```

输出:

```java
Example 1 :
Geek1   10
GEEK1Geek2   30
GEEK1GEEK2Geek3   60
GEEK1GEEK2GEEK3Geek4   100
GEEK1GEEK2GEEK3GEEK4Geek5   150
GEEK1GEEK2GEEK3GEEK4GEEK5Geek6   210

Example 2 :
Geek1   10
Geek2   20
GEEK2Geek3   50
GEEK2GEEK3Geek4   90
Geek5   50
Geek6   60
```

**注意:** parallelPrefix()是用非常基本的操作来解释的，你可以通过编写不同的 lambda 表达式来尝试对数组执行不同的操作。

**既然可以顺序做，为什么还要用 parallelPrefix()呢？**

*   并行操作在更大尺寸的阵列上要快得多，但它通常取决于机器。
*   我们在执行并行操作时使用 lambda，这减少了代码中的行数，使其更加优雅和可读

**参考文献:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/arrays . html](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html)
本文由 **Sumit Ghosh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。