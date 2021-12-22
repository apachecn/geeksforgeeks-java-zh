# JavaTuples setKey()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-setkey-method/](https://www.geeksforgeeks.org/java-tuples-setkey-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的**设置键()**方法用于设置键值类对象的键。此方法只能用于 javatuples 库的 KeyValue 类对象。它返回另一个键值类对象，键作为元素作为参数传递，值来自以前的键值类对象。

**方法声明:**

```java
public <X> KeyValue<X, B> setKey(X key)
```

**语法:**

```java
KeyValue<X, B> KeyValueClassObject = KeyValue.setKey(X key)
```

**返回值:**这个方法返回另一个 KeyValueClassObject，Key 作为作为参数传递的元素，值来自之前的 KeyValueClassObject。

下面的程序说明了使用 setKey()方法的各种方法:

**例 1** :

```java
// Below is a Java program to set
// key in a KeyValue pair

import java.util.*;
import org.javatuples.KeyValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a KeyValue object
        KeyValue<Integer, String> kv
            = KeyValue.with(Integer.valueOf(1),
                            "A computer science portal");

        // Using setKey() method
        KeyValue<String, String> kv1 = kv.setKey("GeeksforGeeks");

        // Printing the returned KeyValue
        System.out.println(kv1);
    }
}
```

**输出**:

```java
[GeeksforGeeks, A computer science portal]

```

**例 2** :

```java
// Below is a Java program to set
// key in a KeyValue pair

import java.util.*;
import org.javatuples.KeyValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a KeyValue object
        KeyValue<Integer, String> kv
            = KeyValue.with(Integer.valueOf(1),
                            "1");

        // Using setKey() method
        KeyValue<String, String> kv1 = kv.setKey("One");

        // Printing the returned KeyValue
        System.out.println(kv1);
    }
}
```

**输出**:

```java
[One, 1]

```