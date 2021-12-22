# Java 通用地图

> 原文:[https://www.geeksforgeeks.org/generic-map-in-java/](https://www.geeksforgeeks.org/generic-map-in-java/)

Java [数组](https://www.geeksforgeeks.org/arrays-in-java/)将项目存储在有序集合中，并且可以使用**索引**(一个整数)来访问这些值。而[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)作为**键/值**对存储。使用 HashMap，我们可以存储项目或值，这些值可以被任何类型的索引/键访问，无论是整数、字符串、双精度、字符还是任何用户定义的数据类型。

> 散列表中的映射来自**键→值**

自 Java 1.2 以来，HashMap 就是 Java 的一部分。它实现了 [java.util.Map](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口。

**什么是通用地图，它与术语 HashMap 有何不同？**

术语[通用](https://www.geeksforgeeks.org/generics-in-java/#:~:text=Generics%20means%20parameterized%20types.,methods%2C%20classes%2C%20and%20interfaces.&text=An%20entity%20such%20as%20class,type%20is%20called%20generic%20entity.) 仅仅是允许类型(整数、双精度、字符串等)的想法。或任何用户定义的类型)作为方法、类或接口的参数。例如，java 中所有内置的集合，如[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)**[HashSet](https://www.geeksforgeeks.org/hashset-in-java/)[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)等。使用泛型。**

**简单语言中的通用映射可以概括为:**

```java
Map< K, V > map = new HashMap< K, V >(); 
```

**其中 **K 和 V** 用于指定在 HashMap 声明中传递的**泛型类型参数**。我们可以添加任何类型，无论是整数、字符串、浮点、字符还是任何用户定义的类型来代替上面语法中的 K 和 V，以指定我们可以初始化我们想要的 HashMap。**

****示例:****

**假设**键**的类型为**字符串**，对应的**值**的类型为**整数，**那么我们可以将其初始化为:**

```java
Map< String , Integer > map = new HashMap< String ,Integer >(); 
```

**地图现在只能接受[字符串](https://www.geeksforgeeks.org/strings-in-java/#:~:text=Strings%20in%20Java%20are%20Objects,entirely%20new%20String%20is%20created.)实例作为关键字，[整数](https://www.geeksforgeeks.org/java-lang-integer-class-java/)实例作为值。**

### **访问通用地图**

**这可以通过使用 put()和 get()函数来实现。**

****1。** [put()](https://www.geeksforgeeks.org/map-put-method-in-java-with-examples/) : 用于向哈希表添加新的键/值对。**

****2。** [get()](https://www.geeksforgeeks.org/map-get-method-in-java-with-examples/) : 用于获取特定按键对应的值。**

****例**:**

```java
Map< Integer, String > map = new HashMap<>();

// adding the key **123** and value
// corresponding to it as **abc** in the map
map.put( 123, "abc");     
map.put(65, "a");
map.put(2554 , "GFG");
map.get(65); 
```

****输出:****

```java
a 
```

### **迭代一般映射**

**[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)有两个集合进行迭代**。**一个是[键集()](https://www.geeksforgeeks.org/map-keyset-method-in-java-with-examples/)另一个是[值()](https://www.geeksforgeeks.org/hashmap-values-method-in-java/)。**

****示例:**使用迭代器()方法**

```java
Map<Integer, Integer> map = new HashMap<>;

//adding key, value pairs to the Map

// iterate keys.
Iterator<Integer> key   = map.keySet().iterator();

while(key.hasNext()){
  Integer aKey   = key.next();
  String  aValue = map.get(aKey);
}

Iterator<Integer>  value = map.values().iterator();

while(valueIterator.hasNext()){
  String aString = value.next();
} 
```

****示例:**使用新的 for-loop 或 for-each 循环或泛型 for loop**

```java
Map<Integer, String> map = new HashMap<Integer, String>;

//adding key, value pairs to the Map

//using for-each loop
for(Integer key : map.keySet()) {
    String value = map.get(key);
    System.out.println("" + key + ":" + value);
}

for(String value : map.values()) {
    System.out.println(value);
} 
```

****Java 程序说明地图的用法****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// Generic Map

import java.io.*;
import java.util.*;

class GenericMap {

    public static void main(String[] args)
    {
        // create array of strings
        String arr[]
            = { "gfg",  "code",    "quiz",   "program",
                "code", "website", "quiz",   "gfg",
                "java", "gfg",     "program" };

        // to count the frequency of a string and store it
        // in the map
        Map<String, Integer> map = new HashMap<>();
        for (int i = 0; i < arr.length; i++) {
            if (map.containsKey(arr[i])) {
                int count = map.get(arr[i]);
                map.put(arr[i], count + 1);
            }
            else {
                map.put(arr[i], 1);
            }
        }

        // to get and print the count of the mentioned
        // string
        System.out.println(map.get("gfg"));
        System.out.println(map.get("code"));
    }
}
```

****Output**

```java
3
2
```**