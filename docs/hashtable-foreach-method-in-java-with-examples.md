# Java 中的哈希表 forEach()方法，示例

> 原文:[https://www . geesforgeks . org/hashtable-foreach-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashtable-foreach-method-in-java-with-examples/)

**哈希表类**的 **forEach(双消费者)**方法对哈希表的每个条目执行双消费者操作，直到所有条目都被处理完或者操作抛出异常。双用户操作是以迭代顺序执行的哈希表键值对的函数操作。方法遍历哈希表的每个元素，直到该方法处理完所有元素或者发生异常。操作引发的异常被传递给调用方。

**语法:**

```java
public void 
    forEach(BiConsumer<? super K, ? super V> action)
```

**参数:**该方法取一个参数名**双消费者**，代表每个元素要执行的动作。

**返回:**此方法不返回任何内容。

**异常:**此方法抛出:

*   [T0】 NullPointerException 【T1]: If the specified action is empty.

下面的程序说明了 forEach(双消费者)方法:

**程序 1:**

```java
// Java program to demonstrate
// forEach(BiConsumer) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a table and add some values
        Map<String, Integer>
            table = new Hashtable<>();

        table.put("Pen", 10);
        table.put("Book", 500);
        table.put("Clothes", 400);
        table.put("Mobile", 5000);
        table.put("Booklet", 2500);

        // add 100 in each value using forEach()
        table.forEach((k, v) -> {

            v = v + 100;
            table.replace(k, v);
        });

        // print new mapping using forEcah()
        table.forEach(
            (k, v) -> System.out.println("Key : " + k + ", Value : " + v));
    }
}
```

**输出:**

```java
Key : Booklet, Value : 2600
Key : Clothes, Value : 500
Key : Mobile, Value : 5100
Key : Pen, Value : 110
Key : Book, Value : 600

```

**程序 2:** 显示空指针异常

```java
// Java program to demonstrate
// forEach(BiConsumer) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a table and add some values
        Map<Integer, String>
            table = new Hashtable<>();

        table.put(1, "100RS");
        table.put(2, "500RS");
        table.put(3, "1000RS");

        try {

            // add 100 in each value using forEach()
            table.forEach((k, v) -> {

                v = v + 100;
                table.put(null, v);
            });
        }
        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

T5】输出:

```java
Exception: java.lang.NullPointerException

```

参考文献:[https://docs . Oracle . com/javase/8/docs/API/Java/util/Hashtable . html # forEach-Java . util . function . Bionsumer-](https://docs.oracle.com/javase/8/docs/api/java/util/Hashtable.html#forEach-java.util.function.BiConsumer-)