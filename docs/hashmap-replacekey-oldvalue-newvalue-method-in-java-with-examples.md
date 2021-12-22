# 用示例替换 Java 中的 HashMap(key，oldValue，newValue)方法

> 原文:[https://www . geesforgeks . org/hashmap-replace key-old value-new value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashmap-replacekey-oldvalue-newvalue-method-in-java-with-examples/)

由 **[HashMap 类](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)** 实现的 **[映射界面](https://www.geeksforgeeks.org/map-interface-java-examples/)** 的**替换(K 键，V oldValue，V newValue)** 方法，仅当该键之前映射了指定的旧值时，用于替换指定键的旧值。

**语法:**

```
default boolean replace(K key, V oldValue, V newValue)

```

**参数:**该方法接受三个参数:

*   **key:** is the **key** of the element whose value needs to be replaced.
*   **Old value:** is the old value of **and must be mapped with the provided key.**
*   **New value:** is the new value of **and must be mapped with the specified key.**

**返回值:**如果旧值被替换，该方法返回布尔值**真**，否则**假**。

**异常:**如果指定的键或值为空，并且此映射不允许空键或值，则此方法将抛出:

*   **[null pointerexception](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** , which is thrown if some attributes of the specified key or value prevent it from being stored in this mapping.
*   **非法引数异常**。

**程序 1:**

```
// Java program to demonstrate
// replace(K key, V oldValue, V newValue) method

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

        // provide old value, new value for the key
        // which has to replace it's old value, using
        // replace(K key, V oldValue, V newValue) method
        map.replace("b", 300, 200);

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
// replace(K key, V oldValue, V newValue) method

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

        // provide old value, new value for the key
        // which has to replace it's old value,
        // and store the return value in isReplaced using
        // replace(K key, V oldValue, V newValue) method
        boolean isReplaced = map.replace("b", 200, 500);

        // print the value of isReplaced
        System.out.println("Old value for 'b' was "
                           + "replaced: " + isReplaced);

        // print new mapping
        System.out.println("New HashMap: "
                           + map.toString());
    }
}
```

**输出:**

```
HashMap: {a=100, b=300, c=300, d=400}
Old value for 'b' was replaced: false
New HashMap: {a=100, b=300, c=300, d=400}

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/hashmap . html # replace-K-V-V-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#replace-K-V-V-)