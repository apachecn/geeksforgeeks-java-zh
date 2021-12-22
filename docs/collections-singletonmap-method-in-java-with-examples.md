# Java 中的 Collections singletonMap()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-singletonmap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-singletonmap-method-in-java-with-examples/)

**java.util.Collections** 类的 **singletonMap()** 方法用于返回一个不可变的映射，只将指定的键映射到指定的值。返回的映射是可序列化的。

**语法:**

```java
public static  Map singletonMap(K key, V value)
```

**参数:**该方法以下列参数为自变量:

*   **键–**返回的地图中唯一要存储的键。
*   **值–**返回的映射键映射到的值。

**返回值:**这个方法返回一个只包含指定键值映射的**不可变映射**。

以下是说明*单线图()*方法的示例

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// singletonMap() method
// for <String, String> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create singleton map
            // using singletonMap() method
            Map<String, String>
                map = Collections
                          .singletonMap("key", "Value");

            // printing the singletonMap
            System.out.println("Singleton map is: "
                               + map);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Singleton map is: {key=Value}
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// singletonMap() method
// for <Integer, Boolean> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create singleton map
            // using singletonMap() method
            Map<Integer, Boolean>
                map = Collections
                          .singletonMap(100, true);

            // printing the singletonMap
            System.out.println("Singleton map is: "
                               + map);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Singleton map is: {100=true}
```