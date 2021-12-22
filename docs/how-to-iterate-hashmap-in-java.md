# 如何在 Java 中迭代 HashMap？

> 原文:[https://www . geesforgeks . org/how-iterate-hashmap-in-Java/](https://www.geeksforgeeks.org/how-to-iterate-hashmap-in-java/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 是 Java 集合的一部分，通过将数据存储在(Key，Value)对中，通过另一种类型的索引来访问它们，从而提供 Java Map 接口的基本实现。一个对象被列为另一个对象(值)的键(索引)。如果您尝试插入重复的键，它将替换相应键的元素。为了使用这个类及其方法，需要导入[*Java . util . hashmap*](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)包或其超类。

有许多方法可以迭代 HashMap，下面列出了其中的 5 种:

1.  使用迭代器迭代哈希表 [EntrySet](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/) 。
2.  使用迭代器遍历 HashMap [键集](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/)。
3.  对于每个循环，使用[迭代哈希表。](https://www.geeksforgeeks.org/for-each-loop-in-java/)
4.  使用 Lambda 表达式迭代 HashMap。
5.  使用[流应用编程接口](https://www.geeksforgeeks.org/stream-in-java/)在哈希表中循环。

**方法 1:使用 for 循环遍历 HashMap。**通过 for 循环迭代 HashMap，使用 *getValue()* 和[T5】getKey()](https://www.geeksforgeeks.org/keystore-getkey-method-in-java-with-examples/)函数。

**实现:**在下面给出的代码中， [entrySet()](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/) 用于返回映射元素的集合视图。根据下面给出的代码:

*   set.getValue()从集合中获取值。
*   set.getKey()从集合中获取密钥。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate over HashMap

// Importing Map and HashMap classes
// from package names java.util
import java.util.HashMap;
import java.util.Map;

// Class for iterating HashMap using for loop
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a HashMap
        Map<String, String> foodTable
            = new HashMap<String, String>();

        // Inserting elements to the adobe HashMap
        // Elements- Key value pairs using put() method
        foodTable.put("A", "Angular");
        foodTable.put("J", "Java");
        foodTable.put("P", "Python");
        foodTable.put("H", "Hibernate");

        // Iterating HashMap through for loop
        for (Map.Entry<String, String> set :
             foodTable.entrySet()) {

            // Printing all elements of a Map
            System.out.println(set.getKey() + " = "
                               + set.getValue());
        }
    }
}
```

**Output**

```java
P = Python
A = Angular
H = Hibernate
J = Java
```

**方法 2:使用 forEach 迭代 HashMap。**在第二种方法中， [forEach](https://www.geeksforgeeks.org/foreach-loop-vs-stream-foreach-vs-parallel-stream-foreach/) 函数迭代键值对。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate over HashMap
// Iterating HashMap using forEach

// Importing Map and HashMap classes
// from package names java.util
import java.util.HashMap;
import java.util.Map;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating hash map
        Map<Character, String> charType
            = new HashMap<Character, String>();

        // Inserting data in the hash map.
        charType.put('J', "Java");
        charType.put('H', "Hibernate");
        charType.put('P', "Python");
        charType.put('A', "Angular");

        // Iterating HashMap through forEach and
        // Printing all. elements in a Map
        charType.forEach(
            (key, value)
                -> System.out.println(key + " = " + value));
    }
}
```

**Output**

```java
P = Python
A = Angular
H = Hibernate
J = Java
```

**方法 3:使用迭代器遍历 HashMap。**在这个方法中，迭代器被用来迭代 HashMap 中的每个映射对，如下面的 java 程序所示。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate over HashMap
// Using Iterator

// Importing classes from java.util package
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;

public class GFG {

    // Main driver method
    public static void main(String[] arguments)
    {
        // Creating Hash map
        Map<Integer, String> intType
            = new HashMap<Integer, String>();

        // Inserting data(Key-value pairs) in hashmap
        intType.put(1, "First");
        intType.put(2, "Second");
        intType.put(3, "Third");
        intType.put(4, "Fourth");

        // Iterator
        Iterator<Entry<Integer, String> > new_Iterator
            = intType.entrySet().iterator();

        // Iterating every set of entry in the HashMap
        while (new_Iterator.hasNext()) {
            Map.Entry<Integer, String> new_Map
                = (Map.Entry<Integer, String>)
                      new_Iterator.next();

            // Displaying HashMap
            System.out.println(new_Map.getKey() + " = "
                               + new_Map.getValue());
        }
    }
}
```

**Output**

```java
1 = First
2 = Second
3 = Third
4 = Fourth
```

**方法 4:使用 Lambda 表达式迭代 HashMap】**

lambda 表达式是一小段接受参数并返回值的代码。Lambda 表达式类似于方法，但是它们不需要名称，并且可以直接在方法的主体中实现。最简单的 lambda 表达式包含一个参数和一个表达式:

```java
parameter -> expression
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Iterating HashMap using Lambda Expressions- forEach()
// Importing Map and HashMap classes
// from java.util package
import java.util.HashMap;
import java.util.Map;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating hash map
        Map<Character, String> charType
            = new HashMap<Character, String>();

        // Inserting elements(key-value pairs)
        // in the hash map ( Custom inputs)
        charType.put('A', "Apple");
        charType.put('B', "Basketball");
        charType.put('C', "Cat");
        charType.put('D', "Dog");

        // Iterating through forEach and
        // printing the elements
        charType.forEach(
            (key, value)
                -> System.out.println(key + " = " + value));
    }
}
```

**Output**

```java
A = Apple
B = Basketball
C = Cat
D = Dog
```

**方法 5:** **使用流应用编程接口**在哈希表中循环

下面的例子在流应用编程接口的帮助下迭代哈希表。

流应用编程接口用于处理对象集合。

流不会改变原始的数据结构，它们只根据流水线方法提供结果

**步骤:**

*   首先调用 **entrySet()。stream()** 返回 stream 对象的方法。
*   接下来 **forEach 方法**，迭代 entrySet()中的输入对象。请参见下面的代码。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate over HashMap
// Loop through a HashMap using Stream API

// Importing classes from
// package named 'java.util'
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;

// HashMap class
public class GFG {

    // Main driver method
    public static void main(String[] arguments)
    {
        // Creating hash map
        Map<Integer, String> intType
            = new HashMap<Integer, String>();

        // Inserting data(key-value pairs) in HashMap
        // Custom inputs
        intType.put(1, "First");
        intType.put(2, "Second");
        intType.put(3, "Third");
        intType.put(4, "Fourth");

        // Iterating every set of entry in the HashMap, and
        // printing all elements of it
        intType.entrySet().stream().forEach(
            input
            -> System.out.println(input.getKey() + " : "
                                  + input.getValue()));
    }
}
```

**Output**

```java
1 : First
2 : Second
3 : Third
4 : Fourth
```