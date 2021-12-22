# Java . util . arrays . parallels tall()、Arrays.setAll()在 Java 中

> 原文:[https://www . geesforgeks . org/Java-util-arrays-parallels tall-arrays-set all-Java/](https://www.geeksforgeeks.org/java-util-arrays-parallelsetall-arrays-setall-java/)

**先决条件:**

*   [Java 8 中的 Lambda 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)
*   [输入操作界面](https://docs.oracle.com/javase/8/docs/api/java/util/function/IntUnaryOperator.html)

java 8 中的[数组类](https://www.geeksforgeeks.org/array-class-in-java/)引入了 parallelSetAll 和 SetAll。

*   **parallels tall():**通过计算每个元素的函数，将指定数组中的所有元素设置在 **parallel** 中。
    **语法:**

```java
public static void parallelSetAll(double[] arr, IntToDoubleFunction g)
Parameters :
arr :  Array to which the elements to be set 
g : It is a function that accepts index of an array 
and returns the computed value to that index
```

*   变化:

```java
parallelSetAll(double[] arr, IntToDoubleFunction g)
parallelSetAll(int[] arr, IntUnaryOperator g)
parallelSetAll(long[] arr, IntToLongFunction g)
parallelSetAll(T[] arr, IntFunction g)
```

*   **setAll() :** 它通过计算每个元素的函数来设置指定数组中的所有元素。
    **语法:**

```java
public static void setAll(int[] arr, IntUnaryOperator g)
Parameters :
    arr :  Array to which the elements to be set
 g : It is a function that accepts index of an array 
and returns the computed value to that index
```

*   变化:

```java
setAll(double[] array, IntToDoubleFunction generator)
setAll(int[] array, IntUnaryOperator generator)
setAll(long[] array, IntToLongFunction generator)
setAll(T[] array, IntFunction generator)
```

**平行筛分()vs 筛分()**

可以看出，这两个函数产生相同的输出，但是并行处理速度更快，因为它并行(即一次)执行数组上的更改，而 SetAll()更新数组的每个索引(即一个接一个)。虽然 SetAll()在较小的数组上运行得更快，但是当数组较大时，parallelSetAll()会接管 setAll()。

**示例**

让我们看一个例子**并行高(int[] arr，Inturnaryooperator g)**和**设置所有(int[]数组，Inturnaryooperator 生成器)**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate setAll()
// and ParallelSetAll()
import java.util.Arrays;
import java.util.function.IntUnaryOperator;
class GFG
{
    public static void main(String[] args)
    {
        // Declaring arrays of integers
        int[] arr_parallel1 = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,
                                13, 14, 15, 16, 17, 18, 19, 20 };
        int[] arr_parallel2 = Arrays.copyOf(arr_parallel1, arr_parallel1.length);
        int[] arr = Arrays.copyOf(arr_parallel1, arr_parallel1.length);

        // Applying parallelSetAll on Array arr_parallel1
        IntUnaryOperator g = e->
        {
            if (e % 2 == 0)
                return e * e;
            else
                return e;
        };
        Arrays.parallelSetAll(arr_parallel1, g);

        /* Another way of passing the second argument.
        Uncomment to try .
        Arrays.parallelSetAll(arr_parallel1, e -> {
        if (e % 2 == 0)
        return e * e;
        else
        return e;
        }); */
        System.out.println("Example 1: Modifying the values at even"
        + " index and storing the square of index");

        // Printing the modified array
        Arrays.stream(arr_parallel1).forEach(e->System.out.print(e + " "));

        // Applying parallelSetAll on Array arr_parallel2
        Arrays.parallelSetAll(arr_parallel2, e->
        {
            if (arr_parallel2[e] % 2 == 0)
                return arr_parallel2[e] * arr_parallel2[e];
            else
                return arr_parallel2[e];
        });
        System.out.println("\n\nExample 2: Modifying the values when"
                        + "even value is encountered");

        // Printing the modified array
        Arrays.stream(arr_parallel2).forEach(e->System.out.print(e + " "));

        // Applying setAll on Array arr
        Arrays.setAll(arr, e->
        {
            if (e % 2 == 0)
                return e * e;
            else
                return e;
        });
        System.out.println("\n\nExample 3:setAll gives exactly "
                        + "same output as parallelSetAll");

        // Printing the modified array
        Arrays.stream(arr).forEach(e->System.out.print(e + " "));
    }
}
```

输出:

```java
Example 1: Modifying the values at even index and storing the square of index
0  1  4  3  16  5  36  7  64  9  100  11  144  13  196  15  256  17  324  19  

Example 2: Modifying the values when even value is encountered
1  4  3  16  5  36  7  64  9  100  11  144  13  196  15  256  17  324  19  400  

Example 3:setAll gives exactly same output as parallelSetAll
0  1  4  3  16  5  36  7  64  9  100  11  144  13  196  15  256  17  324  19  
```

**示例 2 :** 我们甚至可以传递用户定义数据类型的数组。让我们来看一个例子**设置所有(T[]数组，IntFunction 生成器)**和**并行高(T[] arr，IntFunction g)**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate setAll()
// and ParallelSetAll
import java.util.Arrays;
class GFG {
    // User Defined class Person
    static class Person {
        String name;
        int age;

        // constructor
    public Person(String name, int age)
        {
            this.name = name;
            this.age = age;
        }
    }

    public static void main(String[] args)
    {
        // Declaring Arrays of person
        Person p[] = { new Person("samir", 20),
                       new Person("anil", 25), new Person("amit", 10),
                       new Person("rohit", 17), new Person("Geek5", 19),
                       new Person("sumit", 22), new Person("gourav", 24),
                       new Person("sunny", 27), new Person("ritu", 28) };

        // Applying paralleSetAll on p array
        Arrays.parallelSetAll(p, e->{
            if (p[e].name.startsWith("s"))
                return new Person("You are a geek", 100);
            else
                return new Person(p[e].name, p[e].age);
        });
        System.out.println("Example 1; Modifying the name that starts with s");

        // Printing array elements
        Arrays.stream(p).forEach(e->System.out.println(e.name + "   " + e.age));

        // Declaring another array of person
        Person p1[] = { new Person("samir", 16),
                        new Person("anil", 25), new Person("amit", 10),
                        new Person("rohit", 17), new Person("Geek5", 19),
                        new Person("sumit", 16), new Person("gourav", 24),
                        new Person("sunny", 11), new Person("ritu", 28) };

        // Applying setAll on p1
        Arrays.setAll(p1, e->{
            if (p1[e].age < 18)
                return new Person("Teenager", p1[e].age);
            else
                return new Person(p1[e].name, p1[e].age);
        });

        System.out.println("\n\nExample 2: Modifying name whose"
                           + "age is less than 18");

        // Printing array elements
        Arrays.stream(p1).forEach(e->System.out.println(e.name + "   " + e.age));
    }
}
```

输出:

```java
Example 1; Modifying the name that starts with s
You are a geek   100
anil   25
amit   10
rohit   17
Geek5   19
You are a geek   100
gourav   24
You are a geek   100
ritu   28

Example 2: Modifying name whose age is less than 18
Teenager   16
anil   25
Teenager   10
Teenager   17
Geek5   19
Teenager   16
gourav   24
Teenager   11
ritu   28
```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/arrays . html](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html)
本文由 **Sumit Ghosh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。