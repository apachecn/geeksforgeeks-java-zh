# JavaTuples getKey()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-getkey-method/](https://www.geeksforgeeks.org/java-tuples-getkey-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **getKey()** 方法用于从 KeyValue 类的 TupleClassObject 中获取密钥。此方法只能用于 javatuples 库的 KeyValue 类对象。它返回一个键，该键是出现在键值类对象的索引 0 处的元素。返回的密钥确保类型安全。

**方法声明:**

```java
public A getKey()
```

**语法:**

```java
KeyValue<A, B> KeyValueClassObject = KeyValue.with(A a, B b);
A val = KeyValueClassObject.getKey()
```

**返回值:**该方法返回一个键，该键是出现在 KeyValueClassObject 的索引 0 处的元素。

下面的程序说明了使用 getKey()方法的各种方法:

**例 1** :

```java
// Below is a Java program to get
// a KeyValue value

import java.util.*;
import org.javatuples.KeyValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a KeyValue object
        KeyValue<Integer, String> kv
            = KeyValue.with(Integer.valueOf(1),
                            "GeeksforGeeks");

        // Using getKey() method
        int key = kv.getKey();

        // Printing the Key
        System.out.println(key);
    }
}
```

**输出**:

```java
1

```

**例 2** :

```java
// Below is a Java program to get
// a KeyValue value

import java.util.*;
import org.javatuples.KeyValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a KeyValue object
        KeyValue<String, String> kv
            = KeyValue.with("GeeksforGeeks",
                            "A Computer Science Portal for Geeks");

        // Using getKey() method
        String key = kv.getKey();

        // Printing the Key
        System.out.println(key);
    }
}
```

**输出**:

```java
GeeksforGeeks

```