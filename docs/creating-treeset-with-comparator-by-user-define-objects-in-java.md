# 在 Java 中通过用户定义对象用比较器创建树集

> 原文:[https://www . geesforgeks . org/creating-treeset-with-comparator-by-user-define-objects-in-Java/](https://www.geeksforgeeks.org/creating-treeset-with-comparator-by-user-define-objects-in-java/)

[TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 是 Set 接口的实现类。它遵循自然的排序顺序，或者您可以使用比较器对其进行自定义，并且它也不允许重复。

**语法:**

```java
TreeSet<String> gfg= new TreeSet<>();
```

下面是 TreeSet 的正常实现:

## Java

```java
// Java program for TreeSet
import java.io.*;
import java.util.TreeSet;

class GFG {
    public static void main(String[] args)
    {

        TreeSet<String> gfg = new TreeSet<String>();

        // adding elements in Treeset using add() method
        gfg.add("first");
        gfg.add("second");
        gfg.add("third");
        gfg.add("fourth");
        gfg.add("fifth");

        // iterating over the TreeSet using
        // foreach loop and printing it
        for (String value : gfg) {
            System.out.println(value);
        }
    }
}
```

输出

```java
fifth
first
fourth
second
third
```