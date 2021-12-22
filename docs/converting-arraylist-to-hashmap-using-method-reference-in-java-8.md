# 在 Java 8 中使用方法引用将数组列表转换为 HashMap】

> 原文:[https://www . geesforgeks . org/converting-ArrayList-to-hashmap-using-method-reference-in-Java-8/](https://www.geeksforgeeks.org/converting-arraylist-to-hashmap-using-method-reference-in-java-8/)

数据结构对每个编写代码的人来说都是一个福音。但是有什么方法可以将一个数据结构转换成另一个数据结构呢？嗯，好像有！在本文中，我们将学习如何使用 Java 8 中的方法引用将[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)转换为[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)。

**示例:**

```
Elements in ArrayList are : [Pen, Pencil, Book, Headphones]
Elements in HashMap are :{Pen=3, Pencil=6, Book=4, Headphones=10}
```

**在 Java 8 中，有两种方法可以实现我们的目标:**

1.  使用[λ表达式将数组列表转换为哈希表。](https://www.geeksforgeeks.org/lambda-expressions-java-8/)
2.  使用[方法引用](https://www.geeksforgeeks.org/method-references-in-java-with-examples/)将数组列表转换为哈希表。

**方法:使用方法参考**

与 Lambda 表达式相比，使用方法引用使代码看起来更加清晰。

Lambda 只不过是代码，如果已经有一个做同样事情的方法，那么可以传递方法引用，而不是 Lambda 表达式。

*   **Function.identity()** 指的是将自身作为 HashMap 的键的元素。
*   **String::length** 允许将元素的长度存储为其相关值。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for Converting ArrayList to
// HashMap using method reference in Java 8

import java.io.*;
import java.util.*;
import java.util.function.Function;
import java.util.stream.Collectors;

class GFG {
    public static void main(String[] args)
    {

        // creating arraylist to add elements
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Banana");
        fruits.add("Guava");
        fruits.add("Pineapple");
        fruits.add("Apple");

        // printing contents of arraylist before conversion
        System.out.println("Elements in ArrayList are : "
                           + fruits);

        // creating new hashmap and using method reference
        // with necessary classes for the conversion
        HashMap<String, Integer> res = fruits.stream().collect(Collectors.toMap(
                Function.identity(), String::length,
                (e1, e2) -> e1, HashMap::new));

        // printing the elements of the hashmap
        System.out.println("Elements in HashMap are : "
                           + res);
    }
}
```

**Output**

```
Elements in ArrayList are : [Banana, Guava, Pineapple, Apple]
Elements in HashMap are : {Guava=5, Apple=5, Pineapple=9, Banana=6}

```