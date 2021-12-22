# Java 字符串类行()方法示例

> 原文:[https://www . geesforgeks . org/Java-string-class-line-method-with-examples/](https://www.geeksforgeeks.org/java-string-class-lines-method-with-examples/)

*line()*方法是一种静态方法，它返回从给定的多行字符串 中提取的*行流，由行终止符分隔，如下所示:*

<figure class="table">

| 线路终端器 | 命令 |
| --- | --- |
| 换行字符 | \n |
| 回车符 | \r |
| 回车后紧接着换行 | \r\n |

</figure>

**语法:**

```java
public Stream<String> lines()
```

**返回类型:**多行中按顺序出现的字符串流

插图:

```java
Input  : "Geek \n For \n Geeks \n 2021"
Output :
     Geek
     For
     Geeks
     2021
```

**实施:**

在这里，我们将讨论三个例子，以更好地理解字符串类行()方法对数据结构的作用。

*   为每一个
*   将行流转换为数组列表
*   将行流转换为数组

让我们一个接一个地讨论它们:

**例 1:**forEach**T3】**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing Stream class from
// java.util package
import java.util.stream.Stream;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom input string
        String str
            = " Geeks \n For \n Geeks \r Technical \r\n content \r writer \n Internship";

        // Generating stream of lines from string
        // using line method
        Stream<String> lines = str.lines();

        // print and display the output string
        // using forEach aand scope resolution operator
        lines.forEach(System.out::println);
    }
}
```

**Output**

```java
 Geeks 
 For 
 Geeks 
 Technical 
 content 
 writer 
 Internship
```

**示例 2:** 使用 forEach 将行流式传输到数组列表

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate String class lines() method
// by converting stream of lines to ArrayList 

// Importing ArrayList and Stream class
// from java.util package
import java.util.ArrayList;
import java.util.stream.Stream;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom input string
        String str
            = " Geeks \n For \n Geeks \r Technical \r\n content \r writer \n Internship";

        // Generating stream of lines from string
        // using lines() method
        Stream<String> lines = str.lines();

        // Creating an ArrayList object of String type
        ArrayList<String> arrayList = new ArrayList<>();

        // Now, adding elements to arrayList using forEach
        lines.forEach(arrayList::add);

        // Print and display the ArrayList
        System.out.println(arrayList);
    }
}
```

**Output**

```java
[ Geeks ,  For ,  Geeks ,  Technical ,  content ,  writer ,  Internship]
```

**示例 3:** 要排列的线条流

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate String class lines() method
// by converting stream of lines to array 

// Importing Arrays and Stream class from
// java.util package
import java.util.Arrays;
import java.util.stream.Stream;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom input string
        String str
            = " Geeks \n For \n Geeks \r Technical \r\n content \r writer \n Internship";

        // Generating stream of lines from
        // string using line() method
        Stream<String> lines = str.lines();

        // Converting into array
        // using toArray() method
        Object[] array = lines.toArray();

        // Print and display the array
        // using standard toString() method
        System.out.println(Arrays.toString(array));
    }
}
```

**Output**

```java
[ Geeks ,  For ,  Geeks ,  Technical ,  content ,  writer ,  Internship]
```