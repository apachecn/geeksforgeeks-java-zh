# Java 中的 HashMap forEach(双消费者)方法，示例

> 原文:[https://www . geeksforgeeks . org/hashmap-foreachbiconsumer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashmap-foreachbiconsumer-method-in-java-with-examples/)

**[HashMap 类](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)** 的 **forEach(双消费者)**方法对 HashMap 的每个条目执行双消费者操作，直到所有条目都被处理完或者操作抛出异常。双用户操作是哈希表键值对的函数操作，按照迭代的顺序执行。方法遍历哈希表的每个元素，直到该方法处理完所有元素或者发生异常。操作引发的异常被传递给调用方。

**语法:**

```java
public void forEach(BiConsumer action)
```

**参数:**该方法接受一个双消费者类型的参数**动作**，该参数表示要对 HashMap 元素执行什么动作。

**返回:**此方法不返回任何内容。

**异常:**如果动作为空，该方法抛出**空指针异常**。

下面的程序说明了 forEach(双消费者)方法:

**程序 1:使用动作**

```java
// Java program to demonstrate
// forEach(BiConsumer) method.

import java.util.HashMap;
import java.util.Map;
import java.util.function.BiConsumer;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        Map<String, Integer> map
            = new HashMap<>();

        map.put("geeks", 55);
        map.put("for", 13);
        map.put("geeks", 22);
        map.put("is", 11);
        map.put("heaven", 90);
        map.put("for", 100);
        map.put("geekies like us", 96);

        // creating a custom action
        BiConsumer<String, Integer> action
            = new MyBiConsumer();

        // calling forEach method
        map.forEach(action);
    }
}

// Defining Our Action in MyBiConsumer class
class MyBiConsumer implements BiConsumer<String, Integer> {

    public void accept(String k, Integer v)
    {
        System.out.print("Key = " + k);
        System.out.print("\t Value = " + v);
        System.out.println();
    }
}
```

**遍历哈希表输出:**

```java
Key = geeks     Value = 22
Key = for     Value = 100
Key = is     Value = 11
Key = heaven     Value = 90
Key = geekies like us     Value = 96

```

**程序二:**

```java
// Java program to demonstrate
// forEach(BiConsumer) method.

import java.util.HashMap;
import java.util.Map;
import java.util.function.BiConsumer;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a HashMap
        // and add some values
        Map<String, Integer> map
            = new HashMap<>();

        map.put("geeks", 55);
        map.put("for", 13);
        map.put("geeks", 22);
        map.put("is", 11);
        map.put("heaven", 90);
        map.put("for", 100);
        map.put("geekies like us", 96);

        // creating an action
        BiConsumer<String, Integer> action
            = new MyBiConsumer();

        // calling forEach method
        map.forEach(action);
    }
}

// Defining Our Action in MyBiConsumer class
class MyBiConsumer implements BiConsumer<String, Integer> {

    public void accept(String k, Integer v)
    {
        System.out.println("Key: " + k
                           + "\tValue: " + v);

        if ("for".equals(k)) {
            System.out.println("Its the "
                               + "highest value\n");
        }
    }
}
```

**输出:**

```java
Key: geeks    Value: 22
Key: for    Value: 100
Its the highest value

Key: is    Value: 11
Key: heaven    Value: 90
Key: geekies like us    Value: 96

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/hashmap . html # forEach-Java . util . function . bicon summer-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#forEach-java.util.function.BiConsumer-)