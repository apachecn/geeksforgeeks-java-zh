# 如何用 Java 创建线程安全的 ConcurrentHashSet？

> 原文:[https://www . geesforgeks . org/how-to-create-thread-safe-concurrenthashset-in-Java/](https://www.geeksforgeeks.org/how-to-create-a-thread-safe-concurrenthashset-in-java/)

创建**线程安全的 ConcurrentHashSet** 在 JDK 8 之前是不可能的，因为 java.util.concurrent 包没有一个名为 ConcurrentHashSet 的类，但是从 JDK 8 开始，新添加的 keySet(默认)和 newKeySet()方法在 java 中创建了一个 ConcurrentHashSet，该类由 ConcurrentHashMap 支持。

**ConcurrentHashSet** 可以使用 **ConcurrentHashMap** 来创建，因为它允许我们使用 ***keySet(默认值)*** 和 ***newKeySet()*** 方法来返回 Set，这恰好是一个合适的 Set。这使我们能够访问必要的功能，如**包含()、移除()、**等。这些方法只能在 ConcurrentHashMap 类中使用，不能在 ConcurrentMap 接口中使用，所以我们需要使用 ConcurrentHashMap 引用变量来保存引用，或者我们可以使用类型转换来转换存储在 ConcurrentHashMap 变量中的 ConcurrentHashMap 对象。

这种方法的问题是只有一个映射而没有集合，并且它不能使用虚拟值在 ConcurrentHashMap 上执行集合操作。当一些方法需要一个 Set 时，你不能通过，所以它不是很有用。

另一种方法是调用 keySet()方法，keySet()方法实际上返回一个集合，在这个集合中可以执行和传递 Set 操作，但是这个方法有它的局限性，我们不能向这个键集中添加新元素，因为它会抛出一个 UnsupportedOperationException。

由于所有这些限制，引入了 newKeySet()方法，该方法返回一个由给定类型的 ConcurrentHashMap 支持的集合，其中的值是布尔值。

**如何使用 newKeyset()创建 ConcurrentHashSet】**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Create the ConcurrentHashMap
ConcurrentHashMap<String, Integer> map
    = new ConcurrentHashMap<>();

// Create the set by newKeySet() method of ConcurrentHashMap
Set<String> set = map.newKeySet();

// add() method
set.add("geeksforgeeks");
set.add("geeks");

// contains() method to check whether the element present or
// not it will return boolean value (true or false)
set.contains("geeks");

// remove() method to remove an element from set
set.remove("geeksforgeeks");
```

上面提到的这个例子不是在 Java 中创建线程安全集合的唯一方法。

**使用** **键集的并发哈希表(默认值):**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Create ConcurrentHashMap
ConcurrentHashMap<String, Integer> map
    = new ConcurrentHashMap<>();

// Create Set using the map
Set<String> set
    = map.keySet(246); // 246 is any default value

set.add("GeeksForGeeks"); // Value will remain same as 246
                          // but we will ge no error.

// We can use all the functions like contains(),remove(),etc.
// as discussed in the previous code snippet
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Create ConcurrentHashMap
ConcurrentHashMap<String, Integer> map
    = new ConcurrentHashMap<>();

// Create Set using the map
Set<String> set
    = map.keySet(246); // 246 is any default value

set.add("GeeksForGeeks"); // Value will remain same as 246
                          // but we will ge no error.

// We can use all the functions like contains(),remove(),etc.
// as discussed in the previous code snippet
```

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement thread safe ConcurrentHashSet

import java.io.*;
import java.util.Set;
import java.util.concurrent.ConcurrentHashMap;

class GFG {
    public static void main (String[] args) {

        // Creating a map 
        ConcurrentHashMap<String,Integer> map = new ConcurrentHashMap<>();

          map.put("Geeks",246);
          map.put("GeeksforGeeks",246);
          map.put("Java", 200);
          map.put("Java 8",200);
          map.put("Threads", 300);

          // Creating set using keySet()
          Set concSet = map.keySet();

          System.out.println("Initial set: " + concSet);

          // If we want to add element is the set like
          // concSet.add("Element"); this will throw an UnsupportedOperationExcetpion

          // Now as mentioned in the avobe format we have to
        // create the set using newKeySet()
          Set <String> penNameSet = ConcurrentHashMap.newKeySet();

        penNameSet.add("Flair");
        penNameSet.add("Reynolds");
        penNameSet.add("Cello");

          // Print the set
          System.out.println("before adding element into concurrent set: " + penNameSet);

          // Adding new Element in the set
          penNameSet.add("Classmate");

          // Print again to see the change
          System.out.println("after adding element into concurrent set: " + penNameSet);

          // Check element present or not
          if(penNameSet.contains("Reynolds"))
        {
          System.out.println("YES");
        }
          else
        {
          System.out.println("NO");
        }

          // We can check directly like this and it will return a boolean value
          System.out.println(penNameSet.contains("Reynolds"));

          // Remove any element from set
          penNameSet.remove("Cello");
          System.out.println("after removing element from concurrent set: "
                                    + penNameSet);

    }
}
```

**Output**

```java
Initial set: [Threads, Java, GeeksforGeeks, Geeks, Java 8]
before adding element into concurrent set: [Cello, Reynolds, Flair]
after adding element into concurrent set: [Cello, Classmate, Reynolds, Flair]
YES
true
after removing element from concurrent set: [Classmate, Reynolds, Flair]
```

这些是在 Java 8 中创建 **ConcurrentHashSet** 的方法。JDK 8 API 拥有所有主要特性，比如 lambda 表达式和 streams，以及这些使编写代码变得容易的小变化。

**以下是 CopyOnWriteArraySet 的一些重要属性:**

*   它最适合非常小的应用程序，只读操作的数量远远超过变量操作，并且在遍历过程中需要防止线程之间的干扰。
*   它的线是安全的。
*   栅格不支持变量删除操作。
*   遍历迭代器的速度很快，不会遇到其他线程的干扰。
*   在构建迭代器时，再生器能够保持数组的快照不变。