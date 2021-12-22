# foreach()循环 vs Stream foreach()vs Parallel Stream foreach()

> 原文:[https://www . geesforgeks . org/foreach-loop-vs-stream-foreach-vs-parallel-stream-foreach/](https://www.geeksforgeeks.org/foreach-loop-vs-stream-foreach-vs-parallel-stream-foreach/)

### [foreach()循环](https://www.geeksforgeeks.org/for-each-loop-in-java/)

*   **没有使用 lambda 运算符:**Java 中的 foreach 循环不使用任何 Lambda 操作，因此可以对我们在 foreach 循环中用于迭代的列表之外的任何值应用操作。foreach 循环通过将列表的每个元素存储在一个局部变量上并执行我们想要的任何功能来迭代集合或数组。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class GFG {

    public static void main(String[] args)
    {
        String[] arr = { "1", "2", "3" };
        int count = 0;

        String[] arr1 = { "Geeks", "For", "Geeks" };

        for (String str : arr) {
            System.out.print(arr1[count++]);
        }
    }
}
```

**Output:** 

```
GeeksForGeeks
```

*   在这里，计数操作甚至可以作为循环外的变量，因为它在 foreach 循环的范围内。

*   **可用于所有集合和数组:**可用于 Java 中所有集合和数组的迭代。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class GFG {

    public static void main(String[] args) throws Exception
    {

        String[] arr = { "1", "2", "3" };
        int count = 0;

        String[] arr1 = { "Geeks", "For", "Geeks" };

        for (String str : arr) {
            System.out.print(arr1[count++]);
        }
    }
}
```

**Output:** 

```
GeeksForGeeks
```

*   **返回语句在循环内工作:**函数可以在循环内的任意时间点返回值。例如，如果我们想只打印任何集合或数组的前 2 个值，然后我们想返回任何值，这可以在 Java 中的 foreach 循环中完成。下面的代码用于打印数组的第二个元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class GFG {

    public static String frechlop(String[] geek)
    {
        int count = 0;
        for (String var : geek) {
            if (count == 1)
                return var;
            count++;
        }
        return "";
    }

    public static void main(String[] args)
        throws Exception
    {

        String[] arr1 = { "Geeks", "For", "Geeks" };
        String secelt = frechlop(arr1);
        System.out.println(secelt);
    }
}
```

**Output:** 

```
For
```

### [溪流()。forEach()](https://www.geeksforgeeks.org/stream-foreach-method-java-examples/)

*   **使用λ运算符:[流中的:](https://www.geeksforgeeks.org/stream-foreach-method-java-examples/)**()。forEach() ，lambdas 被使用，因此不允许对循环外的变量进行操作。只有对相关集合的操作是可能的。在这种情况下，我们可以通过单行代码对集合执行操作，这使得编码变得容易和简单。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import Java.util.*;
public class GFG {

    public static void main(String[] args) throws Exception
    {

        List<String> arr1 = new ArrayList<String>();
        int count = 0;
        arr1.add("Geeks");
        arr1.add("For");
        arr1.add("Geeks");
        arr1.stream().forEach(s -> {
            // this will cause an error
            count++;

            // print all elements
            System.out.print(s);
        });
    }
}
```

*   **注意:**操作“count++”会导致错误，因为 lambda 操作本身不允许任何外部变量操作。

*   **仅用于迭代集合:**流()。forEach()仅用于访问集合，如集合和列表。它也可以用于访问数组。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;
public class GFG {

    public static void main(String[] args) throws Exception
    {

        String[] arr1 = { "Geeks", "for", "Geeks" };

        // The next line will throw error
        // as there is no such method as stream()
        arr1.stream().forEach(
            s -> { System.out.print(s); });
    }
}
```

*   **Return 语句在这个循环内不起作用，但是函数调用非常容易调用:**
    循环内的 Return 语句不起作用。获取第二个元素的相同功能不能在同一个 forEach()方法中完成。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import Java.util.*;

public class GFG {

    static String second(List<String> list)
    {
        list.stream().forEach(
            s
            -> {
                // The next line will throw error
                // as no return allowed

                // if(s=="For")return s;

            });
        return "null";
    }

    public static void main(String[] args) throws Exception
    {

        List<String> arr1 = new ArrayList<String>();
        arr1.add("Geeks");
        arr1.add("For");
        arr1.add("Geeks");
        String f = second(arr1);
        System.out.println(f);
    }
}
```

**Output:** 

```
null
```

### 并行 foreach()

*   **研究多线程概念:**stream()的唯一区别。foreach()和并行 forEach()是并行 forEach()中给出的多线程特性。这比 foreach()和 stream.forEach()快得多。比如 stream()。forEach()它还使用 lambda 符号来执行功能。
    提供多线程特性的例子如下。
    很明显，由于 parallelStream 的多线程特性，输出永远不会以相同的顺序打印字符串。

这

**Output:** 

```
ForGeeksGeeks
```

### 表格差异

<figure class="table">

| foreach()循环 | 流()。foreach()循环 | 并行流()。foreach()循环 |
| --- | --- | --- |
| 不使用 Lambda 运算符 | 使用了 Lambda 运算符 | 使用了 Lambda 运算符 |
| 可用于访问数组和集合 | 只能访问集合 | 只能访问集合 |
| 返回或控制语句在循环中工作 | 返回或控制语句在循环中不起作用 | 返回或控制语句在循环中不起作用 |
| 没有多线程，因此缓慢的数据是有序的 | 没有多线程，因此缓慢的数据是有序的 | 它是多线程的，因此速度非常快，顺序也不同 |

</figure>