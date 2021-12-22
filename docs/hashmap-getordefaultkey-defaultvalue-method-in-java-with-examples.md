# Java 中的 HashMap getOrDefault(key，defaultValue)方法，示例

> 原文:[https://www . geesforgeks . org/hashmap-getordefaultkey-defaultvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashmap-getordefaultkey-defaultvalue-method-in-java-with-examples/)

**[映射接口](https://www.geeksforgeeks.org/map-interface-java-examples/)** 的 **getOrDefault(Object key，V defaultValue)** 方法，由 **[HashMap 类](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)** 实现，用于获取用指定 key 映射的值。如果没有值与提供的键映射，则返回默认值。

**语法:**

```java
default V getOrDefault(Object key, V defaultValue)
```

**参数:**此方法接受两个参数:

*   **key:** is the **key** of the element whose value must be obtained.
*   **Default value:** is the default value of **that must be returned, if there is no value mapped with the specified key.**

**返回值:**此方法返回用指定键映射的**值**，否则返回**默认值**。

**程序 1:**

```java
// Java program to demonstrate
// getOrDefault(Object key, V defaultValue) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 200);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide key whose value has to be obtained
        // and default value for the key. Store the
        // return value in k
        int k = map.getOrDefault("b", 500);

        // print the value of k returned by
        // getOrDefault(Object key, V defaultValue) method
        System.out.println("Returned Value: " + k);
    }
}
```

**输出:**

```java
HashMap: {a=100, b=200, c=300, d=400}
Returned Value: 200

```

**程序二:**

```java
// Java program to demonstrate
// getOrDefault(Object key, V defaultValue) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 200);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide key whose value has to be obtained
        // and default value for the key. Store the
        // return value in k
        int k = map.getOrDefault("y", 500);

        // print the value of k returned by
        // getOrDefault(Object key, V defaultValue) method
        System.out.println("Returned Value: " + k);
    }
}
```

**输出:**

```java
HashMap: {a=100, b=200, c=300, d=400}
Returned Value: 500

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/hashmap . html # getOrDefault-Java . lang . object-V-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#getOrDefault-java.lang.Object-V-)