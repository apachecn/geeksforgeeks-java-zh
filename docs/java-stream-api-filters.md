# Java 流应用编程接口–过滤器

> 原文:[https://www.geeksforgeeks.org/java-stream-api-filters/](https://www.geeksforgeeks.org/java-stream-api-filters/)

在本文中，我们将学习 Java 流过滤器应用编程接口。我们会报道，

1.[流过滤器](https://www.geeksforgeeks.org/stream-filter-java-examples/) API 如何工作。

2.按对象属性筛选。

3.按索引筛选。

4.按自定义对象属性筛选。

**流过滤器应用编程接口**

过滤器应用编程接口采用[谓词](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-8-predicate-with-examples/&sa=U&ved=2ahUKEwiq8K-r2tvsAhV1zDgGHTy7DjcQFjACegQIBxAC&usg=AOvVaw0YJ2JCn2wZz2kTEUPUTlGe)。谓词是一个函数接口。它接受任何类型的参数并返回布尔值。如果函数返回 true，则该元素将被考虑用于管道中的下一个应用编程接口。否则，该元素将被过滤掉。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code for Stream filter
// (Predicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.

import java.io.*;
import java.util.stream.Stream;

class StreamFilterExample {
    public static void main(String[] args)
    {
        // create a stream of strings
        Stream<String> myStream
            = Stream.of("Like", "and", "Share",
                        "https://www.geeksforgeeks.org/");

        // only string starting with "http://" will be
        // considered for next API(forEach)
        myStream.filter(x -> x.startsWith("https://"))
            .forEach(System.out::println);
    }
}
```

**Output**

```java
https://www.geeksforgeeks.org/

```

**按对象属性过滤**

按对象属性筛选使用 java 运算符。下面的示例解释了如何根据对象的属性进行筛选。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate 
// filter by Object properties

import java.io.*;
import java.util.stream.Stream;

class FilterByObjectProperties {

    public static void filterByEvenElements()
    {
        // create integer array
        Integer[] myArray
            = new Integer[] { 1, 4, 5, 7, 9, 10 };

        // create a stream and filter by
        // even numbers predicate
        Stream.of(myArray)
            .filter(x -> x % 2 == 0)
            .forEach(System.out::println);
    }

    public static void filterByStartsWith()
    {
        // create String array
        String[] myArray
            = new String[] { "stream",   "is",  "a",
                             "sequence", "of",  "elements",
                             "like",     "list" };

        // create a stream and filter by
        // starting string predicate
        Stream<String> myStream = Stream.of(myArray);
        myStream.filter(x -> x.startsWith("s"))
            .forEach(System.out::println);
    }

    public static void filterByStartsWithVowelsRegex()
    {
        // create string array
        String[] myArray
            = "I am 24 years old and I want to be in Tier I company"
                  .split(" ");

        // create a stream on myArray
        Stream<String> myStream = Stream.of(myArray);

        // filter by matching vowels regular expression
        myStream.filter(x -> x.matches("(a|e|i|o|u)\\w*"))
            .forEach(System.out::println);
    }

    public static void main(String[] args)
    {
        // filters a stream by even elements
        filterByEvenElements();
        System.out.println("======");

        // filters a stream by starting string
        filterByStartsWith();
        System.out.println("======");

        // filters a stream by starting vowel
        filterByStartsWithVowelsRegex();
    }
}
```

**Output**

```java
4
10
======
stream
sequence
======
am
old
and
in

```

**按对象索引过滤**

按索引过滤有两种方式。

**1。原子整数**

我们需要使用 **AtomicInteger** ，因为谓词期望[最终变量](https://www.geeksforgeeks.org/final-keyword-java/)作为参数。只要过滤函数(谓词)返回布尔值，我们就可以使用任何表达式。这里，AtomicInteger 的 [getAndIncrement()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/atomicinteger-getandincrement-method-in-java-with-examples/&sa=U&ved=2ahUKEwjd3s7B39vsAhV3yTgGHaO7C6MQFjAAegQIAhAB&usg=AOvVaw0WDKayNrCy7kRIioF1fLz6) 方法将当前值增加 **1** ，并返回最终的 int 值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate 
// filter by Object Indices
// using AtomicInteger

import java.io.*;
import java.util.stream.Stream;
import java.util.concurrent.atomic.AtomicInteger;

class FilterByObjectIndex {

    public static void filterByIndexUsingAtomic()
    {
        // create a string array
        String[] myArray
            = new String[] { "stream",   "is",  "a",
                             "sequence", "of",  "elements",
                             "like",     "list" };

        // create a stream on myArray
        Stream<String> myStream = Stream.of(myArray);

        // create an AtomicInteger
        AtomicInteger i = new AtomicInteger(0);

        // increment the i value by 1 everytime
        // if it is even, print the current element
        myStream.filter(x -> i.getAndIncrement() % 2 == 0)
            .forEach(System.out::println);
    }

    public static void main(String[] args)
    {
        // filter by Object index
        filterByIndexUsingAtomic();
    }
}
```

**Output**

```java
stream
a
of
like

```

**2。输入流方法**

我们可以使用 **Intstream** 并根据索引映射数组元素。这里我们首先创建一个由一系列数字组成的**数据流**。检查一个数字是否为偶数，然后用数组元素覆盖/映射该整数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate 
// filter by Object properties
// using IntSteam Approach

import java.io.*;
import java.util.stream.IntStream;
class FilterByObjectIndexUsingIntStream {

    public static void filterByIndexUsingStream()
    {
        // create an array of Strings
        String[] myArray
            = new String[] { "stream",   "is",  "a",
                             "sequence", "of",  "elements",
                             "like",     "list" };

        // create instream on range of integers
        // filter by even integer and map
        // the integer to the Object of myArray
        IntStream.rangeClosed(0, myArray.length - 1)
            .filter(x -> x % 2 == 0)
            .mapToObj(x -> myArray[x])
            .forEach(System.out::println);
    }

    public static void main(String[] args)
    {
        filterByIndexUsingStream();
    }
}
```

**Output**

```java
stream
a
of
like

```

**按自定义属性过滤**

我们可以使用任何 Java 对象属性进行过滤。这里我们按年龄过滤。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate 
// filter by Custom Properties

import java.io.*;
import java.util.List;
import java.util.Arrays;
import java.util.stream.Stream;
class CustomFiltering {

    // Employee class
    class Employee {

        // attributes of an Employee
        String name;
        int age;

        // constructor
        Employee(String name, int age)
        {
            this.name = name;
            this.age = age;
        }

        // Override toString to print
        // provided content when an Object
        // is printed
        @Override public String toString()
        {
            return "Employee [name=" + name + "]";
        }
    }

    public static void filterByAge()
    {
        // create list of Employees
        List<Employee> myList = Arrays.asList(
            new GFG().new Employee("Ram", 25),
            new GFG().new Employee("Kumar", 40),
            new GFG().new Employee("Rakesh", 35));

        // create a stream on the list
        // filter by age of an employee
        myList.stream()
            .filter(x -> x.age >= 35)
            .forEach(System.out::println);
    }

    public static void main(String[] args)
    {
        filterByAge();
    }
}
```

**Output**

```java
Employee [name=Kumar]
Employee [name=Rakesh]

```

我们还可以创建一个自定义的过滤函数。该函数必须接受一个参数并返回一个布尔值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Custom filter

import java.io.*;
import java.util.stream.Stream;
class CustomFilterExample {

    public static void filterByCustomProperties()
    {
        // create a string array
        String[] myArray
            = new String[] { "madam", "please", "refer",
                             "link",  "on",     "racecar" };

        // filter using a custom method
        Stream.of(myArray)
            .filter(x -> palindrome(x))
            .forEach(System.out::println);
    }

      // checks if palindrome or not
    public static boolean palindrome(String s)
    {
        if (s.length() <= 1)
            return true;
        else
            return (s.charAt(0) == s.charAt(s.length() - 1))
                && palindrome(
                       s.substring(1, s.length() - 1));
    }

    public static void main(String[] args)
    {
        filterByCustomProperties();
    }
}
```

**Output**

```java
madam
refer
racecar

```