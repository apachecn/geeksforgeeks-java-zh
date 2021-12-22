# 用示例替换 Java 中的 HashMap(键，值)方法

> 原文:[https://www . geesforgeks . org/hashmap-replace key-value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashmap-replacekey-value-method-in-java-with-examples/)

由 **[HashMap 类](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)** 实现的 **[映射界面](https://www.geeksforgeeks.org/map-interface-java-examples/)** 的**替换(K 键，V 值)**方法，只有在该键之前映射了某个值的情况下，才用于替换指定键的值。

**语法:**

```
public V replace(K key, V value)

```

**参数:**该方法接受两个参数:

*   **key:** is the **key** of the element whose value needs to be replaced.
*   **value:** is the new value of **and must be mapped with the provided key.**

**返回值:**该方法返回与指定键关联的**上一个值**。如果没有映射这样的键，那么如果实现支持空值，则返回**空值**。

**异常:**如果指定的键或值为空，并且此映射不允许空键或值，则此方法将抛出:

*   **[null pointerexception](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** , which is thrown if some attributes of the specified key or value prevent it from being stored in this mapping.
*   **非法引数异常**。

**程序 1:**

```
// Java program to demonstrate
// replace(K key, V value) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 300);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide value for the key which has
        // to replace it's current value,
        // using replace(K key, V value) method
        map.replace("b", 200);

        // print new mapping
        System.out.println("New HashMap: "
                           + map.toString());
    }
}
```

**输出:**

```
HashMap: {a=100, b=300, c=300, d=400}
New HashMap: {a=100, b=200, c=300, d=400}

```

**程序二:**

```
// Java program to demonstrate
// replace(K key, V value) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 300);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide value for the key which has
        // to replace it's current value, and will
        // store the value in k using the
        // replace(K key, V value) method
        int k = map.replace("b", 200);

        // print the value of k
        System.out.println("Previous value of 'b': "
                           + k);

        // print new mapping
        System.out.println("New HashMap: "
                           + map.toString());
    }
}
```

**输出:**

```
HashMap: {a=100, b=300, c=300, d=400}
Previous value of 'b': 300
New HashMap: {a=100, b=200, c=300, d=400}

```

**程序 3:**

```
// Java program to demonstrate
// replace(K key, V value) method

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("a", 100);
        map.put("b", 300);
        map.put("c", 300);
        map.put("d", 400);

        // print map details
        System.out.println("HashMap: "
                           + map.toString());

        // provide value for the key which is
        // not mapped previously and store the
        // return value in Integer k, using
        // replace(K key, V value) method
        Integer k = map.replace("e", 200);

        // print the value of k
        System.out.println("Value of k, returned "
                           + "for key 'e': " + k);

        // print new mapping
        System.out.println("New HashMap: "
                           + map.toString());
    }
}
```

**输出:**

```
HashMap: {a=100, b=300, c=300, d=400}
Value of k, returned for key 'e': null
New HashMap: {a=100, b=300, c=300, d=400}

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/hashmap . html # replace-K-V-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#replace-K-V-)